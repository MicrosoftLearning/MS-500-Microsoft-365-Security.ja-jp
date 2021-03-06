# モジュール 11 - ラボ 1 - 演習 1 - DLP ポリシーを管理する  


Adatum のセキュリティ管理者、Holly Dickson としてのロールで、Microsoft 365 を仮想ラボ環境でデプロイしました。Microsoft 365 パイロット プロジェクトを進めているのですが、次のステップでは Adatum でデータ損失防止 (DLP) ポリシーを実装します。まず、カスタム DLP を作成してから、メール メッセージのアーカイブと機密データが含まれているメールに関連した DLP ポリシーをテストします。 

### タスク 1 - カスタム設定で DLP ポリシーを作成する

この演習では、 セキュリティ/コンプライアンス センターでデータ損失防止ポリシーを作成し、ユーザーが機密データを共有することを防止します。作成する DLP ポリシーでは、ユーザーが米国社会保障番号の含まれたコンテンツを共有できないようにします。

1. まだ、クライアント 1 VM (**LON-CL1**) に **LON-CL1\Admin** アカウントとしてログインし、Microsoft 365 に **Holly Dickson** としてログインしているはずです。 

2. **Microsoft Edge** で、「Office 365 コンプライアンス センター」 タブがまだ開いているはずです。その場合は、それを選択して次の手順に進みます。閉じている場合は、新しいタブで `https://protection.office.com` に移動します。

3. **セキュリティ/コンプライアンス センター**の左側のナビゲーション ペインで 「**データ損失防止**」 を選択してから 「**ポリシー**」 を選択します。

4. **「ポリシー」** ウィンドウで **「+ ポリシーの作成」** を選択し、新しいデータ損失防止ポリシーを作成するウィザードを起動します。

5. 「**テンプレートの利用またはカスタム ポリシーの作成**」 ページの左側のペインで 「**カスタム**」、真ん中のペインで 「**カスタム ポリシー**」 を選択します。ただし、既定でどちらのオプションもすでに選択されています (そうでない場合は、ここで選択します)。「**次へ**」 を選択します。

6. 「**ポリシーの名前を設定**」 ページで 「**名前**」 フィールドに `Social Security DLP Policy` と入力し、「**説明**」 フィールドには `Protect social security numbers from being shared` と入力します。「**次へ**」 を選択します。

7. 「**場所の選択**」ページで、**Exchange メール、SharePoint、OneDrive、Teams チャットとチャネル メッセージ**の場合は「**オン**」、デバイス、**Microsoft Cloud App Security、オンプレミス リポジトリ**の場合は「**オフ**」を選択してから、「**次へ**」を選択します。

8. **「詳細な DLP ルールのカスタマイズ」** で、**「+ ルールの作成」** を選択します。

9. 「**ルールの作成**」ページの「**名前**」フィールドに「**社会保障番号**」と入力します。

10. 「**条件**」で、「**+ 条件を追加**」、「**コンテンツに含まれるもの**」の順にクリックします。

11. **Default** の値をそのままにして、**Add v** を選択し、**Sensitive info types** を選択します。

12. 検索フィールドに `social` と入力し、Enter キーを押し、検索結果が表示されるまで待ちます。

13. 検索結果のリストで 「**米国の社会保障番号 (SSN)**」 チェックボックスを選択し、「**追加**」 を選択します。

14. 「**条件の追加**」をクリックし、「**コンテンツは Microsoft 365 から共有**」を選択します。

15. この下のフィールドで、**組織内の人だけが表示されている**ことを確認します。

16. 「**アクション**」セクションまで下にスクロールし、

17. **+ 追加とアクション*をクリックし、

18. 「**アクセスの制限または Microsoft 365 の場所のコンテンツの暗号化**」を選択します

19. **「アクセスの制限または Microsoft 365 のコンテンツの暗号化」** ボックスをチェックし、**「全員をブロック」** を選択します。

20. 「**インシデント レポート**」まで下にスクロールします。

21. 「**管理者アラートおよびレポートでこの重大度レベルを使用する**」フィールドで「**中**」を選択します。

22. 「**ルールの一致が発生したときに管理者に送信してアラートを送信する**」のスライダー バーを「**オン**」に移動します。

23. **「保存」** を選択します。

24 **「次へ」** をクリックします。

24. **「テストを行うかポリシーを有効にする」** ページで、**「すぐに有効にします」** を選択し、**「次へ」** を選択します。

25. **「送信」** をクリックします

これで、組織内で送信または共有されるメールとドキュメントで米国の社会保障番号をスキャンする DLP ポリシーが作成されました。


# 演習 2 に進みます。 
