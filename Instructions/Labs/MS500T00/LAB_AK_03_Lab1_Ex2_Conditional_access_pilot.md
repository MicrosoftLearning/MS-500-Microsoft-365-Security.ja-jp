---
ms.openlocfilehash: 122bdaf3d5a1dbd026c22458869ac41fc06d4380
ms.sourcegitcommit: 25b9793190d40e69ed31815267fb6754397768bd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/02/2022
ms.locfileid: "137943330"
---
# <a name="module-3---lab-1---exercise-2----mfa-conditional-access-complete-an-azure-multi-factor-authentication-pilot-roll-out"></a>モジュール 3 - ラボ 1 - 演習 2 -  MFA 条件付きアクセス (Azure Multi-Factor Authentication Pilot のロールアウトを完了する)


この演習では、Azure portal にログインするときに、Azure Multi-Factor Authentication (Azure MFA) を有効にする条件付きアクセスポリシーを構成します。 このポリシーは、パイロット ユーザーの特定のグループにデプロイされ、テストされます。 条件付きアクセスを使用する Azure MFA のデプロイは、組織および管理者にとって、従来の強制方法よりも大幅に高い柔軟性を持つ方法です。

- Azure Multi-Factor Authentication の有効化
- Azure Multi-Factor Authentication をテストする


### <a name="task-1-enable-azure-multi-factor-authentication"></a>タスク 1:Azure Multi-Factor Authentication を有効にする

1.  グローバル管理者の Holly Dickson としてログインしている Azure portal に戻ります。

1.  ハブで **[Azure Active Directory]** に移動します、

1.  **[グループ]** をクリックして **[+ 新規グループ]** をクリックします。

     ![Screenshot](../Media/cb9c5324-cbb6-476e-9c7d-1920de301d40.png)

1.  次の情報を入力して **[次へ]** を選択します。

      * グループの種類: `Security`
      * グループ名: `MFA Pilot`
      * グループの説明: `MFA Pilot Group`
      * メンバーシップの種類: `Assigned`
      * メンバー:[`Lynne Robbins`] を選択します
  
  
      ![Screenshot](../Media/5457b62d-dc78-4043-bd72-3d7901bbcd71.png)
  
2.  **Azure Active Directory** を参照し、 **[セキュリティ]** をクリックし、 **[ポリシー]** ブレードで **[条件付きアクセス]** を選択します。


3.  **[+ 新しいポリシー]** を選択し、 **[新しいポリシーの作成]** を選択します。


4.  ポリシーに `MFA Pilot` という名前を付けます。
5.  **[ユーザーまたはワークロード ID]** で、 **[選択されているユーザーまたはワークロード ID は 0 です]** をクリックします。 **[ユーザーとグループの選択]** ラジオ　ボタンを選択し、 **[ユーザーとグループの選択]** チェック ボックスをオンにします。
    * `MFA Pilot` のパイロット グループを選択します。
    * **[選択]** をクリックします。

6.  **[クラウド アプリまたはアクション]** セクションで、 **[クラウド アプリ、アクション、または認証コンテキストが選択されません]** をクリックします。
    * **[選択]** をクリックします。 Azure portal のクラウド アプリは `Microsoft Azure Management` です。これを選択します。
    * **[アプリを選択]** をクリックします。

7.  **[条件]** セクションはスキップします
8.  **[アクセス制御]** セクションの **[許可]** で、 **[選択されているコントロールは 0 です]** をクリックし、 **[アクセス権の付与]** ラジオ ボタンが選択されていることを確認します。
    * **[多要素認証を要求する]** チェック ボックスをオンにします。
    * **[選択]** をクリックします。

9.  **[セッション]** セクションはスキップします
10. **[ポリシーを有効にする]** を **[オン]** に切り替えます。
11. **[作成]**

    **注**:ポリシーが失敗したら、作業内容を確認してから再び **[作成]** をクリックします。 

### <a name="task-2-test-azure-multi-factor-authentication"></a>タスク 2:Azure Multi-Factor Authentication をテストする


条件付きアクセス ポリシーが機能することを証明するには、MFA を必要としないリソースへのログインをテストし、次に MFA を必要とする Azure portal へのログインをテストします。


2.  InPrivate またはシークレット モードで新しいブラウザー ウィンドウを開き、**`https://portal.azure.com`** に移動します。

       * ユーザー Lynne Robbins としてログインします (Lynne のパスワードはおそらくラボのホスティング プロバイダーから提供された MOD 管理者のパスワードと同じです)。登録して Azure Multi-Factor Authentication を使用するよう求められるはずです。
       * ブラウザー ウィンドウを閉じます。



# <a name="end-of-lab"></a>ラボ終了
