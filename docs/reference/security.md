---
title: 安全性-Visual Studio 即時共用 |Microsoft Docs
description: Visual Studio Live Share 有關的安全性功能資訊。
ms.custom: ''
ms.date: 12/17/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 754a740118ef9e6de2463fb3bb0537af350409aa
ms.sourcegitcommit: 100fce9b9bbcd7e6f68d40659bd2760e9537de37
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/29/2019
ms.locfileid: "58640194"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="security-features-of-live-share"></a>Live Share 安全性功能

可讓任意數目的人加入的工作階段中共同編輯、 偵錯和更多功能，在 Visual Studio Live Share 的共同作業工作階段是功能強大。 不過，提供此存取層級，您一定會感興趣 Live Share 所提供的安全性功能。 在本文中，我們將提供一些建議和保護您的環境所需的選項。

**如有任何共同作業工具，請記住，您應該只共用您的程式碼、 內容和應用程式與您信任的人。**

## <a name="connectivity"></a>連線能力

在 Visual Studio Live Share 的所有連線都都 SSH 或 SSL 加密，並針對提供集中的服務驗證，以確保只有在共同作業工作階段才能存取其內容。 根據預設，Live Share 嘗試直接連線，而且會回復雲端轉送上如果無法建立客體和主機之間的連線。 請注意，Live Share 雲端轉送不會保存任何透過它路由傳送的流量不會不"窺探 」 以任何方式的流量。 不過，如果您不希望使用轉送，您可以變更一律直接連線的設定。

若要深入了解這些行為和 Live Share 連線需求改變，請參閱 **[Live Share 的連線需求](connectivity.md)**。

## <a name="invitations-and-join-access"></a>邀請和加入存取權限

每次您啟動新的共同作業工作階段時，會產生 Live Share**新的唯一識別碼**，都會在 [邀請] 連結。 下列連結提供穩固、 安全的基礎，邀請您信任的連結中的識別碼是 「 非猜到"，而是因為那些_只適用於單一的共同作業工作階段期間_。

### <a name="removing-an-unexpected-guest"></a>移除未預期的來賓

為主機，會自動通知您只要來賓加入共同作業工作階段。

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-join-notification.png" width="100%" alt="Visual Studio Code join notification" />
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vs-join-notification.png" width="100%" alt="Visual Studio join notification"/>
    </td>
</tr>
</table>

更棒的是，通知可讓您移除已加入如果基於某些原因您不知道它們的來賓。 （例如，如果您不小心全公司的聊天系統上張貼您的連結，而且是隨機的員工加入。）只要按一下 [移除] 按鈕，會出現在通知中，將會退出共同作業工作階段。

在  **VS Code**，即使您已經解除聯結的通知，您也可以在那之後移除參與者。 藉由在 [總管] 中或在 VS Code 活動列中的 [自訂] 索引標籤中開啟 Live Share 檢視，您可以將滑鼠停留或參與者名稱上按一下滑鼠右鍵並選取 「 移除參與者 」 圖示或選項。

![移除在 VS Code 中的參與者](../media/vscode-remove-participant.png)

### <a name="requiring-guest-approval"></a>需要來賓核准

一般而言，會加入共同作業工作階段的參與者**登入 Live Share**使用 Microsoft 公司或學校帳戶 (AAD)、 個人 Microsoft 帳戶或 GitHub 帳戶。 而 「 通知 + 移除 」 預設值適用於登入的使用者提供良好的混合的速度和取得這些客體的控制項，您可能想要**鎖定項目**您做的事情機密的更多。

此外，在某些情況下，強制執行登入加入共同作業的所有來賓工作階段可能會造成問題。 範例包括要求至 Live Share 為來賓，教室/學習案例中，加入新的人員或與沒有其中一個支援的帳戶類型的任何人共同作業時。 基於這些理由，Live Share 可讓屬於使用者**未登入時**加入為共同作業工作階段**唯讀**來賓。 雖然主機所需**核准**這些客體，才能夠加入預設情況下，您可能要或不允許這些 「 匿名 」 客體一律改為核准。

#### <a name="requiring-guest-approval-for-signed-in-users"></a>需要來賓核准登入使用者

如果您想要避免登入加入您的共同作業工作階段，直到您有 「 已核准 」 它們的來賓，變更下列設定：

* 在  **VS Code**，將下列新增至 settings.json (檔案 > 喜好設定 > 設定):

    ```json
    "liveshare.guestApprovalRequired": true
    ```

* 在  **Visual Studio**，設定工具 > 選項 > Live Share > 設為 True 的 「 需要客體核准 」。

    ![使用來賓核准設定反白顯示的 visual Studio 設定視窗](../media/vs-setting-guestapproval.png)

從這裡開始，您將要求核准加入每個來賓。

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-join-approval.png" width="100%" alt="Visual Studio Code join approval request" />
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vs-join-approval.png" width="100%" alt="Visual Studio join approval request"/>
    </td>
</tr>
</table>

為來賓，如果您加入工作階段主機已啟用，這項設定的其中您便會在狀態列中就會收到通知或加入 Live Share 正在等候要核准的主機的對話方塊。

#### <a name="auto-rejecting-or-accepting-users-that-are-not-signed-in-anonymous"></a>自動拒絕或接受未登入 （匿名） 的使用者

如上面所述，Live Share 可設定為允許**您尚未登入的使用者**加入為共同作業工作階段**唯讀**來賓。  雖然這些 **"anonymous"的來賓都必須輸入一個名稱**聯結時，簡單的名稱不會提供相同等級的保證，做為實際的登入。 因此，**根據預設，主應用程式會提示核准**不論 「 需要客體核准 」 任何匿名訪客設定上面所述。

您可以**永遠拒絕**（停用匿名訪客） 或**一律接受**匿名使用者相反地，如下所示：

* 在**VS Code**，將`liveshare.anonymousGuestApproval`settings.json 中 (檔案 > 喜好設定 > 設定) 來`accept`， `reject`，或`prompt`（預設值） 視需要。

* 在  **Visual Studio**，設定工具 > 選項 > Live Share > 匿名訪客 「 核准 」 到接受、 拒絕、 或命令提示字元 （預設值） 做為適當。

 **不論如何，請記住，您應該只會傳送 Live Share 信任的邀請給您的連結。**

## <a name="controlling-file-access-and-visibility"></a>控制檔案存取權和可見性

為來賓，Live Share 遠端模型可讓您快速的讀取/寫入存取檔案和資料夾主應用程式已與您共用而不需要同步處理專案的整個內容。 您因此可以獨立地瀏覽並將在整個共用的檔案樹狀目錄中編輯檔案。 **不過，能夠這麼做可能會產生一些風險主應用程式。** 在概念上，開發人員可以選擇進入並修改原始程式碼，無論您知情或機密的原始碼或 「 密碼 」 共用的檔案樹狀結構中的某處，請參閱。 因此，主應用程式，您可能不一定想您共用的專案的完整存取客體。 幸好，此遠端模式的好處是，您可以選擇 「 排除 」 不想與任何人共用，而不會犧牲功能檔案。 像是偵錯工作階段，如果他們想要做自己，則通常會需要存取這些檔案仍然會加入來賓。

您可以新增來完成這 **。 vsls.json**檔案到資料夾或共用您的專案。 您加入此 json 格式的檔案的任何設定變更 Live Share 處理檔案的方式。 除了提供直接控制，這些檔案也可以認可至原始檔控制讓複製專案的任何人都將能夠利用其組件上使用任何額外的工作，這些規則。

以下是範例。 vsls.json 檔案：

```json
{
    "$schema": "http://json.schemastore.org/vsls",
    "gitignore":"none",
    "excludeFiles":[
        "*.p12",
        "*.cer",
        "token",
        ".gitignore"
    ],
    "hideFiles": [
        "bin",
        "obj"
    ]
}
```

> [!NOTE]
> 您也可以進行所有的檔案/資料夾您共用**唯讀**當您啟動共同作業工作階段。 請參閱[以下](#read-only-mode)如需詳細資訊。

讓我們逐步解說這些屬性如何變更來賓可以做什麼。

### <a name="properties"></a>屬性

**ExcludeFiles**屬性可讓您指定一份 （非常類似的找到.gitignore 檔案） 的 glob 檔案模式，避免 Live Share 來賓開啟特定檔案或資料夾。 請注意，這是包含案例，例如來賓_遵循或跳至您的編輯位置，共同作業偵錯期間逐步執行到的檔案等移至定義，以及其他任何程式碼瀏覽功能。_ 它適用於您永遠不會想要在任何情況下，例如包含密碼、 憑證或密碼所共用的檔案。 比方說，因為它們控制安全性。 一律會排除 vsls.json 檔案。

**HideFiles**屬性非常類似，但不是的那樣嚴格。 這些檔案只會從檔案樹狀目錄中隱藏。 例如，如果您在偵錯期間，以逐步執行其中一個檔案，它是仍在編輯器中開啟。 如果您沒有.gitignore 檔案設定 （如會發生這個狀況，如果您使用不同的原始檔控制系統），或如果您只想要加強功能已經存在以避免雜亂或混淆，這個屬性就特別有用。

**Gitignore**設定可讓您建立 Live Share 應該如何處理共用資料夾中.gitignore 檔案的內容。 根據預設，.gitignore 檔案中找到任何 glob 會視為 「 hideFiles"屬性中指定。 不過，您可以選擇不同的行為，使用下列值之一：

| 選項    | 結果                                                                                                                 |
| --------- | ---------------------------------------------------------------------------------------------------------------------- |
| `none`    | .gitignore 內容會顯示在檔案樹狀目錄中 （假設它們不會篩選所設定的來賓編輯器） 的來賓給項目。 |
| `hide`    | **預設值。** 處理內.gitignore glob，彷彿"hideFiles"屬性中。                   |
| `exclude` | 處理內.gitignore glob，彷彿"excludeFiles"屬性中。                                 |

缺點`exclude`設定是經常位於.gitignore node_modules 資料夾的內容，但很適合用來逐步執行偵錯期間。 因此，Live Share，支援反向規則，使用"！"excludeFiles 屬性中。 比方說，這。 vsls.json 檔案會排除在 「.gitignore"node_modules 除外的所有項目：

```json
{
    "$schema": "http://json.schemastore.org/vsls",
    "gitignore":"exclude",
    "excludeFiles":[
        "!node_modules"
    ]
}
```

隱藏和排除規則會分別處理，因此如果您仍然想要隱藏 node_modules 為了減少混亂，而不實際將它排除，您可以直接編輯檔案，如下所示：

```json
{
    "$schema": "http://json.schemastore.org/vsls",
    "gitignore":"exclude",
    "excludeFiles":[
        "!node_modules"
    ],
    "hideFiles":[
        "node_modules"
    ]
}
```

### <a name="vslsjson-files-in-sub-folders"></a>。 在子資料夾中的 vsls.json 檔案

最後，如同.gitignore，。 vsls.json 檔案可以放在子資料夾中。 隱藏/排除規則取決於開頭。 vsls.json 檔案中 （如果有的話），您已共用的根資料夾，然後逐步解說在每一個子資料夾中，從有業界成指定的檔案，以尋找。 vsls.json 檔案至處理序。 內容。 往下檔案樹狀目錄的資料夾中的 vsls.json 檔案然後補充 （或覆寫） 建立較高層級的規則。

### <a name="disabling-external-file-sharing"></a>停用外部檔案共用

根據預設，Live Share 也會分享主應用程式會開啟外部共用資料夾的任何檔案 / 方案。 這可讓您輕易就能快速而不必再次共用，以開啟其他相關的檔案。

如果您想要停用這項功能：

* 在  **VS Code**，將下列新增至 settings.json:

    ```json
    "liveshare.shareExternalFiles": false
    ```

* 在  **Visual Studio**，設定工具&gt;選項&gt;Live Share&gt;為 False 的 「 共用外部檔案 」

## <a name="read-only-mode"></a>唯讀模式

有時候當您共用您的程式碼，做為主機時，您不想進行編輯來賓。 您可能需要對來賓來看看一些程式碼，或您的來賓大的數字顯示您的專案，而且不想進行的任何不必要或意外編輯。 即時共用可讓您共用唯讀模式中的專案。

做為主機，共用時，您可以選擇針對共同作業工作階段啟用唯讀模式。 當來賓加入時，它們不能對程式碼中，進行編輯，但您仍然可以看到彼此的資料指標和反白顯示，以及瀏覽專案。

您仍然可以同時偵錯在唯讀模式中的來賓。 來賓不會逐步執行偵錯的程序，，但可以仍會新增或移除中斷點，並檢查變數的能力。 此外，您可以仍然共用伺服器和終端機 （唯讀） 來賓。

您可以深入了解啟動唯讀的共同作業工作階段：[![VS Code](../media/vscode-icon-15x15.png)](../use/vscode.md#share-a-project) [![VS](../media/vs-icon-15x15.png)](../use/vs.md#share-a-project)

## <a name="co-debugging"></a>共同偵錯

當各位困難的編碼問題或 bug 時，讓另一對眼睛，偵錯時可以是非常有用。 Visual Studio Live Share 可讓 「 共同作業偵錯 」 或 「 共同偵錯 」 每次主應用程式啟動偵錯時，偵錯工作階段共用所有來賓。

為主機，您可以完全控制透過偵錯工作階段啟動或停止，但同時偵錯可能會產生一些風險如果您與您不信任的人共用時。 即時共用允許來賓您邀請來執行主控台/REPL 命令，因此沒有**惡意執行者執行命令，您不想執行的風險**。

因此，您應該**只能共置您信任的偵錯。**

深入了解：[![VS Code](../media/vscode-icon-15x15.png)](../use/vscode.md#co-debugging) [![VS](../media/vs-icon-15x15.png)](../use/vs.md#co-debugging)

## <a name="sharing-a-local-server"></a>共用的本機伺服器

共同偵錯時，能夠存取主持人針對偵錯工作階段所提供的不同應用程式連接埠會非常有用。 您可能想要存取在瀏覽器應用程式、 存取本機資料庫，或叫用 REST 端點，從您的工具。 Live Share 可讓您的 「 共用的伺服器 」 可將主機的電腦上的本機連接埠對應到客體的機器上完全相同的連接埠。 為來賓，您接著可以與互動的應用程式完全如同它已在本機執行您的電腦上 (例如主機和客體可以同時存取 web 應用程式上執行 http://localhost:3000)。

不過，在主機中，您應該**謹慎選擇與您共用的連接埠**來賓與只共用應用程式連接埠而不是系統的連接埠。 對於來賓，共用連接埠的行為就如同該伺服器/服務是在他們自己的機器上執行。 這非常有用，但如果共用不適當的連接埠，也可能有風險。 基於這個理由，Live Share 都不會進行任何假設項目應該或不應該共用而不需要的組態設定和主應用程式執行動作。

在 Visual Studio 中， **web 應用程式連接埠**指定在 ASP.NET 專案中是**只偵錯期間會自動共用**以便來賓存取權的 web 應用程式執行時。 不過，您可以關閉這項自動化藉由設定工具 > 選項 > Live Share > 「 共用 web 應用程式偵錯 」 為"False"(如果您偏好。

在 Visual Studio Code，Live Share 嘗試**偵測適當的應用程式連接埠**並加以共用。 不過，您可以將下列內容新增至 settings.json 停用此：

        liveshare.autoShareServers: false

在任一情況下，務必特別小心共用其他連接埠時。

您可以深入了解設定的功能：[![VS Code](../media/vscode-icon-15x15.png)](../use/vscode.md#share-a-server) [![VS](../media/vs-icon-15x15.png)](../use/vs.md#share-a-server)

## <a name="sharing-a-terminal"></a>共用終端機

新式開發經常會運用各種命令列工具。 幸運的是，Live Share 可讓身為主持人的您選擇與來賓「共用終端機」。 共用的終端機可以是唯讀，或是完全共同作業，讓您和您的來賓都能執行命令並看到結果。 為主機，就能夠允許設為其他共同作業者只會看到輸出，或使用任何數目的命令列工具來執行測試時，組建，或甚至是分類環境特定問題。

只有主機就可以開始共用的終端機，以防止從一個啟動和執行您不預期或監看的來賓。 當您啟動終端機中共用做為主機時，您可以指定它應該是唯讀還是讀取/寫入。 當終端機是讀取/寫入時，包括主持人在內的每個人都可以在終端機中輸入，這樣當來賓在進行您不希望的操作時，您輕鬆就能介入。 不過，為了安全起見，您應該**只在確定來賓確實需要讀取/寫入存取權時才提供此權限**，並在您只想要來賓查看您執行之任何命令的輸出時提供唯讀終端機。

在 Visual Studio 中，預設不會共用終端機。 在 VS Code 中自動共用終端機**唯讀**預設。 不過，您可以將下列內容新增至 settings.json 停用此：

```json
"liveshare.autoShareTerminals": false
```

深入了解：[![VS Code](../media/vscode-icon-15x15.png)](../use/vscode.md#share-a-terminal) [![VS](../media/vs-icon-15x15.png)](../use/vs.md#share-a-terminal)

## <a name="aad-admin-consent"></a>AAD 系統管理員同意

當使用 Microsoft 登入支援**工作或學校電子郵件地址**您可能會看到訊息，指出 **「 需要系統管理員核准 」** 時登入。 這是因為 Live Share 其安全性功能需要使用者資訊的 「 讀取 」 權限，而且您的 Azure AD 租用戶會設定為需要 「 系統管理員同意 」 新的應用程式存取目錄的內容。

您的 AD 系統管理員需要以解決此問題，使用下列資訊：

* **應用程式名稱**:Visual Studio 即時共用 （測試人員）
* **應用程式類型**:Web 應用程式
* **應用程式狀態**:生產環境
* **委派的權限**:User.Read
* **應用程式 URL**: https://insiders.liveshare.vsengsaas.visualstudio.com/
* **回覆 URL**: https://insiders.liveshare.vsengsaas.visualstudio.com/auth/redirect/windowslive/

這只需要執行一次使用 Live Share 的任何人。 請參閱[此處](https://docs.microsoft.com/en-us/azure/active-directory/develop/active-directory-v2-scopes#admin-restricted-scopes)並[這裡](https://stackoverflow.com/questions/39861830/azure-ad-admin-consent-from-the-azure-portal)如需詳細資訊。

## <a name="see-also"></a>另請參閱

* [操作說明：使用 Visual Studio Code 共同作業](../use/vscode.md)
* [如何：使用 Visual Studio 共同作業](../use/vs.md)
* [Live Share 的連線需求](connectivity.md)

有問題嗎？ 請參閱[疑難排解](../troubleshooting.md)或[提供意見反應](../support.md)。
