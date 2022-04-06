---
ms.openlocfilehash: 416e635c23e85540deef0775c21548f335342d12
ms.sourcegitcommit: 619124fc7aa1c770a67c77e6bbc16fa13e73f2f0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/04/2022
ms.locfileid: "137821067"
---
# <a name="module-8---lab-1---exercise-1---enable-device-management"></a>モジュール 8 - ラボ 1 - 演習 2 - デバイス管理を有効にする


あなたは、Adatum Corporation のセキュリティ管理者、Holly Dickson で、仮想化ラボ環境で Microsoft 365 がデプロイされています。 このラボでは、Intune を使用してユーザーのデバイスを管理します。

この演習では、Adatum に Enterprise Mobility + Security E5 製品がインストールされていることを確認します。 その後、テスト ユーザー アカウントに割り当てられていることを確認し、Holly Dickson にライセンスを割り当てます。

### <a name="task-1-verify-and-assign-enterprise-mobility--security-licenses"></a>タスク 1:Enterprise Mobility + Security ライセンスを確認して割り当てる

このタスクでは、Adatum が Enterprise Mobility + Security E5 製品をインストールしていることを確認し、利用可能なライセンスの数をチェックします。 その後、ライセンスがテスト ユーザー アカウントに割り当てられていることを確認し、Holly Dickson にライセンスを割り当てます。

1. まだ、クライアント 1 VM (LON-CL1) に **lon-cl1\admin** アカウントとしてログインし、Microsoft 365 に Holly Dickson **(holly@M365xZZZZZZ.onmicrosoft.com)** としてパスワード「**Pa55w.rd**」を使ってログインしているはずです。

2. **Microsoft Edge** では、まだ **Microsoft 365 管理センター** のタブが開いているはずです、その場合は、このタブを選択してください。 そうでない場合は、「 **https://portal.office.com** 」と入力して **Holly** としてサインインします。 **[Microsoft Office Home]** ページで **[管理者]** を選択します。

3. **[Microsoft 365 管理センター]** の左側のナビゲーション ペインで **[課金情報]** を選択し、そこで **[ライセンス]** を選択します。

4. **[ライセンス]** ページで **[Enterprise Mobility + Security E5]** を選択します。

5. **[Enterprise Mobility + Security E5]** ページのユーザー一覧で、パイロット チームのメンバー、**Alex Wilber**、**Joni Sherman**、**Lynne Robbins**、**MOD 管理者** がライセンスを割り当てらえrていることを確認します。

    **注:**  これらのユーザー アカウントは Office 365 テナントの一部として作成されたものです。そのプロセスの間にそれぞれ Office 365 E5 ライセンスと Enterprise Mobility + Security E5 ライセンスが割り当てられています。

6. Enterprise Mobility + Security E5 ライセンスを割り当てられなかったユーザーは、グローバル管理者の Holly Dickson です。 以前のラボで Holly のユーザー アカウントを作成した際、Office 365 E5 ライセンスのみを割り当てるよう指示された可能性があります。 ここで Holly に Enterprise Mobility + Security E5 ライセンスを割り当てます。  Holly がすでに Enterprise Mobility + Security E5 ライセンスを持っている場合は、次のタスクをスキップできます。

    Holly にライセンスを割り当てるため、 **[+ ライセンスの割り当て]** を選択します。

7. **[ユーザーへのライセンスの割り当て]** ページで **[名前または電子メール アドレスの入力]** フィールドを選択し、表示されたユーザー一覧で **[Holly Dickson]** を選択します。

8. **[割り当て]** を選択します。

9. **[ライセンスを Holly Dickson さんに割り当てました]** ウィンドウを閉じます。

10. このラボの残りの部分に備えた、クライアント 1 VM を開いたままにします。

これで、テナントで利用可能な Enterprise Mobility + Security E5 ライセンスを確認し、EMS E5 ライセンスを Holly に割り当てました。



# <a name="proceed-to-lab-1---exercise-2"></a>ラボ 1 - 演習 2 に進む
