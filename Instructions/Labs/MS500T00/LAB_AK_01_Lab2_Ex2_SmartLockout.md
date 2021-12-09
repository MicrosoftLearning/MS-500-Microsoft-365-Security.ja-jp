# モジュール 1 - ラボ 2 - 演習 2 - Azure AD スマート ロックアウトのデプロイ 

Adatum の CTO から Azure AD スマート ロックアウトをデプロイするよう要請されました。ユーザーのパスワードを推測したり、ブルート フォース方法でネットワークに入り込もうとしている不正ユーザーをロックアウトする上で役に立ちます。スマート ロックアウトは、有効なユーザーからのサインインを認識し、攻撃者や他の未知のソースからのサインインとは異なる方法で処理できます。 

CTO は、スマート ロックアウトの実装を希望しています。Adatum のユーザーが引き続き自分のアカウントにアクセスして生産性を維持できるようにする一方、攻撃者をロックアウトするためです。ユーザーが複数回、同じパスワードを使用したり、シンプルすぎるか一般的とみなされるパスワードを使用したりできないようにスマート ロックアウトを構成するよう CTO に依頼されました。 

1. ドメイン コントローラー (**LON-DC1**) のタスクバーで 「**サーバー マネージャー**」 アイコンを選択します (すでに開いている場合)。開いていない場合は開いてください。

2. 「**サーバー マネージャー**」 の右上にあるメニューバーで 「**ツール**」 を選択し、ドロップダウン メニューで 「**グループ ポリシーの管理**」 を選択します。

3. 必要に応じて 「**グループ ポリシーの管理**」 ウィンドウを最大化します。

4. 所属組織のアカウント ロックアウト ポリシーが含まれているグループ ポリシーを編集してください。必要に応じて、ルート コンソール ツリーで **Forest:Adatum.com**、**ドメイン**、**Adatum.com** の順に展開します。  <br/>

‎**Adatum.com**, で **Default Domain Policy** and then select **Edit** in the menu を右クリックします。

5. 「**グループ ポリシー管理エディター**」 ウィンドウを最大化します。

6. 右側のペインの 「**既定のドメイン ポリシー**」 ツリーで 「**コンピューターの構成**」  >  「**ポリシー**」  >  「**Windows の設定**」  >  「**セキュリティの設定**」  >  「**アカウント ポリシー**」 を参照します。

7. 「**アカウント ポリシー**」 フォルダーで 「**アカウント ロックアウト ポリシー**」 を選択します。

8. 右側のペインを見ればわかるように、スマート ロックアウト パラメーターは定義されていません。**Azure AD 管理センター**を使用して、これらの値を割り当てます。   <br/>

9.  **Internet Explorer** で新しいブラウザー タブを開き、`https://portal.azure.com` に移動します。  まだ別のブラウザー タブでサインインしていない場合は、Holly Dickson としてサインインします。**Azure Active Directory** を検索し、「**Azure Active Directory**」 をクリックします。 

10. 「**Adatum Corporation**」: | 「**概要**」 ページで 「**管理**」 セクションの中央ナビゲーション ペインをスクロールダウンし、「**セキュリティ**」 を選択します。

11. 「**セキュリティ**」: | 「**はじめに**」 ウィンドウの 「**管理**」 の中央ペインで 「**認証方法**」 を選択します。

12. 「**認証方法**」:  | 「**ポリシー**」 ページの 「**管理**」 セクションの中央ペインで 「**パスワード保護**」 を選択します。

13. 「**認証方法**」: | 「**パスワード保護**」 ウィンドウの右側にある詳細ペインで以下の情報を入力します。

	- 「**カスタム スマート ロックアウト**」 セクション:

		- 「**ロックアウトしきい値**」: このフィールドは、最初のロックアウトまでアカウントのサインイン失敗が何回まで許可されるのか示します。既定値は 10 です。テスト目的で、Adatum はこれを`3`に設定するよう要請しています。

		- 「**ロックアウト期間 (秒)**」: これは各ロックアウトの時間 (秒数) です。既定値は 60 秒 (1 分) です。Adatum は、これを`90`秒に変更するよう要請しています。

	- 「**カスタム禁止パスワード**」 セクション:

		- 「**カスタム リストの強制**」: 「**はい**」 を選択します。

		- 「**カスタム禁止パスワード リスト**」: 以下の値を入力します (各値の入力後に Enter を押して、各値が別個のラインになるようにしてください):

			- `Password01`

			- `F00tball01`

			- `Se@Hawks1`

			- `Never4get!!`

14. ページ最上部のメニュー バーで 「**保存**」 を選択します。

15. これで禁止パスワードの機能をテストできます。画面の右上コーナーで Holly Dicksons のユーザー アイコンを選択し、「**アカウントを表示**」 をクリックし、表示されたメニューで 「**パスワードの変更**」 を選択します。

16. 新しいタブが開き、「**パスワードの変更**」 ウィンドウが表示されます。「**古いパスワード**」 フィールドに `Pa55w.rd` と入力し、「**新しいパスワードの作成**」 と 「**新しいパスワードの確認**」 フィールドには `Never4get!!` と入力してから 「**送信**」 を選択します。表示されるエラー メッセージに留意してください。

17. ブラウザーで 「**パスワードの変更**」 タブを閉じます。 

18. これでロックアウトしきい値の機能をテストできます。「**マイ ダッシュボード - Azure Active Directory 管理センター**」 タブで、画面右上コーナーにある Holly Dicksons のユーザー　アイコンを選択します。表示されるメニューで 「**サインアウト**」 を選択します。 

19. Holly としてサインアウトした後、「**アカウントを選択する**」 ウィンドウが表示されます。「**別のアカウントを使用する**」 を選択します。 

20. 「**サインイン**」 ウィンドウに **AllanD@M365xZZZZZZ.onmicrosoft.com** と入力し (「ZZZZZZ」はラボ ホスティング プロバイダーから割り当てられたテナント サフィックス ID)、「**次へ**」 を選択します。 

21. 「**パスワードの入力**」 ウィンドウで任意の文字を組み合わせたものを入力し、「**サインイン**」 を選択します。無効なパスワードのエラー メッセージに留意してください。このステップをあと 2 回繰り返します。「**ロックアウトしきい値**」 は 「**3**」 に設定されているため、3 回目の試行後はエラー メッセージが出る点に注意してください。許可のないアクセスを防ぐため、Allan のアカウントは一時的にロックされています。<br/>

	**注:** 先ほど設定した **90 秒のロックアウト期間**を超えるまで、Allan としてログインすることはできません。 

22. 90 秒の経過後、再びログインできるか試してみてください。 

# ラボ終了。
 