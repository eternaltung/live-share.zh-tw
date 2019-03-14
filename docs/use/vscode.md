---
title: 使用 Visual Studio Code-Visual Studio Live Share 共同作業 |Microsoft Docs
description: 一組的 Visual Studio Code 和 Live Share 的共同作業做法。
ms.custom: ''
ms.date: 04/27/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- liveshare
ms.topic: conceptual
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 9285fef38fea9bb164892775521ed2a28fe9ef1b
ms.sourcegitcommit: 4f733c9053848f26da03d47050bcb734f6c98b31
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2019
ms.locfileid: "57255557"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="how-to-collaborate-using-visual-studio-code"></a>操作說明：使用 Visual Studio Code 進行共同作業

取得與共同作業，在 VS Code 中的 Live Share 的準備了嗎？  如果是這樣，您已在正確的位置 ！ 在本文中，我們將引導您了解如何使用某些特定功能在 Visual Studio Live Share 延伸模組適用於 Visual Studio Code。

請注意，此處所述的所有共同作業活動包含單一**共同作業工作階段主機**和一或多個**來賓**。 主持人是啟動共同作業工作階段的人員，而來賓是加入的任何人。

*要尋找的簡易的摘要嗎？請參閱[分享](../quickstart/share.md)或是[聯結](../quickstart/join.md)快速入門改為。*

> [!TIP]
> 您知道您可以「加入自己的共同作業工作階段」嗎？ 這讓您可以自行試用 Live Share，或是啟動 Visual Studio 或 VS Code 的執行個體，並從遠端連線到該執行個體！ 您甚至可以在兩個執行個體中使用相同的身分識別。 趕緊去瞧一瞧！

## <a name="installation"></a>安裝

在開始之前，您必須確定您有 Visual Studio 安裝程式碼符合 Live Share 核心需求的版本。 您將需要**Visual Studio Code (1.22.0 或更高版本)** 上執行：

- **Windows**:7、 8.1 或 10

- **macOS**:Sierra (10.12) 和更新版本唯一。
    - _El Capitan (10.11) 和下面目前不支援因[.NET Core 2.0 需求](https://go.microsoft.com/fwlink/?linkid=872315)。_

- **Linux**：64 位元的 Ubuntu 桌面 16.04 +、 Fedora 工作站 27 + CentOS 7

    - 即時共用需要的數字[Linux 必要條件](#linux-install-steps)可能提示您安裝。
    - _因為不支援 32 位元 Linux [.NET Core 2.0 需求](https://go.microsoft.com/fwlink/?linkid=872314)。_
    - ARM 也目前不支援。
    - 請參閱[Linux 安裝詳細資料](../reference/linux.md)如需有關使用下游和其他散發套件的發行項。

之後就能輕鬆下載並安裝 Visual Studio Live Share 延伸模組：

1. 安裝<a href="https://code.visualstudio.com/">Visual Studio Code</a>
2. [下載](https://aka.ms/vsls-dl/vscode)和從 marketplace 安裝 Visual Studio Live Share 延伸模組。
3. 重新載入 Visual Studio Code
4. 等候相依性，以下載並安裝 （請參閱狀態列）。<br/>
    ![完成安裝](../media/vscode-finishing-install.png)
5. **Linux**：如果您看到通知關於安裝遺漏的程式庫：
    1. 在通知中，按一下 [安裝]。
    2. 輸入您的系統管理員 (sudo) 密碼提示時。
    3. 重新啟動 VS Code 時完成。

下載並使用 Visual Studio Live Share 即表示您同意[授權條款](https://aka.ms/vsls-license)和[隱私權聲明](https://www.microsoft.com/en-us/privacystatement/EnterpriseDev/default.aspx)。 如果您遇到問題，請參閱[疑難排解](../troubleshooting.md)。

[![下載](../media/download.png)](https://aka.ms/vsls-dl/vscode)

### <a name="linux-install-steps"></a>Linux 安裝步驟

Linux 是變化極大的環境，而且可以複雜而難以取得使用與大量的桌面環境，以及散發套件。 如果您決定要支援的版本**Ubuntu 桌面**（16.04 +） 或**Fedora 工作站**（27 +）、 **CentOS 7**而且只會使用**VS 的官方發行版程式碼**，您應該會發現處理程序直接了當。 但是，您會使用非標準組態或下游的通訊群組，可能會或可能不會遇到一些營運。 請參閱[Linux 安裝詳細資料](../reference/linux.md)如需詳細資訊。

#### <a name="install-linux-prerequisites"></a>安裝 Linux 必要條件

某些 Linux 版本遺漏 Live Share 需要運作的程式庫。 根據預設，Live Share 會嘗試偵測並安裝您的 Linux 必要條件。 Live Share 遇到的問題，可以源自遺漏要求您安裝它們的權限的程式庫時，您會看到快顯通知。

![顯示訊息，Linux 必要條件的快顯通知已遺失](../media/vscode-linux-prereq-missing.png)

當您按一下 「 安裝 」 時，終端機視窗會出現您要輸入您的系統管理員 (sudo) 密碼，以繼續。 假設此作業成功完成，重新啟動 Visual Studio Code，您應該會就緒 ！ 您也可以查看**[因發行版本的祕訣](../reference/linux.md#tips-by-distribution)** 其他提示和因應措施如果有的話。

如果您看到訊息，指出指令碼不支援您的散發套件，請參閱 < **[社群支援的散發套件的秘訣](../reference/linux.md#tips-for-community-supported-distros)** 社群共用與我們的資訊。

如果您**不想為您執行命令的 VS Code**，您也可以選擇重新執行此指令碼的最新版本隨時以手動方式從終端機視窗中執行下列命令：

    wget -O ~/vsls-reqs https://aka.ms/vsls-linux-prereq-script && chmod +x ~/vsls-reqs && ~/vsls-reqs

#### <a name="linux-browser-integration"></a>Linux 瀏覽器整合

Visual Studio 即時共用通常**不需要額外的安裝步驟**若要啟用在 Linux 上的瀏覽器整合。

時間不常見，在某些散發套件上您**可能會通知您的系統管理員 (sudo) 密碼，就需要**完成安裝程序。 終端機視窗會出現告知您要安裝的瀏覽器啟動。 只要輸入您的密碼提示時，並按 enter 鍵以關閉 終端機視窗中的安裝完成之後。

您可以閱讀更多關於這為何需要及即時的共用位置將檔案放**[此處](../reference/linux.md#linux-browser-integration)**。 請注意，即使您無法取得瀏覽器整合工作，您仍然可以**[手動加入共同作業的工作階段](../use/vscode.md#join-manually)**。

## <a name="sign-in"></a>登入

若要共同作業，您必須登入 Visual Studio Live Share，讓每個人都知道您的身分。 這是純粹的安全性量值，而且並未**不**您參加任何行銷或其他參考資料的活動。 您可以使用登入 Microsoft 個人帳戶 (例如@outlook.com)，Microsoft 支援工作或學校帳戶 (AAD) 或 GitHub 帳戶。 登入很簡單。

**按一下 **的 「 共用 」 狀態列的項目或按**Ctrl + Shift + P / Cmd + Shift + P** ，然後選取 「 即時共用：使用瀏覽器登入 」 的命令。

![VS 程式碼登入 按鈕](../media/vscode-sign-in-button.png)

通知會出現要求您使用網頁瀏覽器登入。 按一下 「 啟動登入 」 會開啟您完成登入程序所使用的瀏覽器。 只需關閉瀏覽器完成。

![使用網頁瀏覽器登入要求的快顯通知](../media/vscode-sign-in-toast.png)

> **Linux 使用者：** 您可能會提示您輸入使用者程式碼，如果您使用較舊版本的 Live Share (v0.3.295 或以下版本)。 更新延伸模組的最新版本，或按一下 「 需要疑難排解嗎？ 」 連結登入之後，以查看程式碼。 請參閱[以下進一步了解](#sign-in-using-a-user-code)。

如果您在瀏覽器中的登入程序完成後，Visual Studio Code 可不會挑出您的登入，請參閱[登入使用使用者程式碼](#sign-in-using-a-user-code)。 否則，請參閱[疑難排解](../troubleshooting.md#sign-in)如需其他提示。

### <a name="sign-in-using-a-user-code"></a>使用使用者程式碼登入

如果您正在使用 VS Code 的問題不會收取已完成的登入，您可以改為輸入 「 使用者程式碼 」。

1. 按下**Ctrl + Shift + P / Cmd + Shift + P**並執行 「 即時共用：使用使用者程式碼登入 」 的命令。

2. 針對您用來完成登入程序，應該會出現在瀏覽器。

    > [!NOTE]
    > 如果未自動出現在瀏覽器，開啟[這個位置](https://insiders.liveshare.vsengsaas.visualstudio.com/auth/login)在瀏覽器並登入。

3. 當您在中，按一下 "時遇到問題嗎？ 如使用者程式碼的指示，請按一下這裡 」 以查看使用者程式碼。

    ![在瀏覽器中的使用者程式碼的圖片](../media/vscode-user-code-browser.png)

4. 複製使用者程式碼。

5. 最後，使用者程式碼貼到 [輸入] 欄位出現時執行命令，然後按 enter 鍵以完成登入程序。

    ![使用者程式碼的輸入欄位的圖片](../media/vscode-user-code.png)

## <a name="using-the-live-share-viewlet"></a>使用 Live Share viewlet

安裝 Visual Studio Live Share 之後, 自訂索引標籤會加入 VS Code 活動列的影響。 在此索引標籤中，您可以存取共同作業的所有 Live Share 函式。 此外，當您共用，或加入共同作業工作階段，檢視也會出現在 [總管] 索引標籤，以便讓您存取所有這些函式。

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-custom-tab.png" width="100%" alt="Live Share custom tab" />
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-explorer-view.png" width="100%" alt="Live Share explorer view"
</tr>
</table>

使用這些檢視中，您可以看到共用的程式碼中的參與者的位置，請按一下按照、 專注的參與者存取共用的伺服器與終端機，和其他參與者。

## <a name="using-the-scoped-command-menu"></a>使用已設定領域的命令功能表

此外，所有的 Visual Studio Live Share 函式都是從 Visual Studio Code 中 「 命令選擇區 」 藉由按下 Ctrl + Shift + P 可存取 / Cmd + Shift + P 或 f1 鍵。 您可以輸入"live share"來找到完整的命令清單。

因為這份清單可能會很長，您會發現您更輕鬆地利用可從 [狀態] 列的已設定領域的命令功能表。 按一下登入 / 命令可供您使用相關的語境清單會立即顯示在狀態列中的工作階段狀態圖示。

![VS 程式碼的工作階段狀態圖示](../media/vscode-share-state.png)

## <a name="share-a-project"></a>共用專案

下載並安裝 Visual Studio Live Share 之後, 請遵循下列步驟來啟動共同作業工作階段，並以邀請同事與您合作。

1. **登入**

    安裝 Live Share 延伸模組、 重新載入，並等待相依性，以完成安裝之後, 您會想要讓其他的共同作業者知道您的身分登入。 請參閱[登入](#sign-in)如需詳細資訊。

2. **開啟資料夾**

    您可以使用您的一般工作流程來開啟資料夾、 專案或方案，您想要分享您的來賓。

3. **[選用]更新隱藏或排除的檔案**

    根據預設，Live Share**隱藏**.gitignore 檔案，在您從來賓的共用資料夾中參考的任何檔案/資料夾。 **隱藏**檔案可防止客體的檔案樹狀結構中出現。 **排除**套用更嚴格的規則，會防止 Live Share 開啟客體中的情況下，像移至定義，或如果您在偵錯，或 「 遵循 」 時逐步執行至檔案的檔案。 如果您想要不同的檔案/排除隱藏 **。 vsls.json**檔案可以新增至您的專案，使用這些設定。 請參閱[控制檔案存取權和可見性](../reference/security.md#controlling-file-access-and-visibility)如需詳細資訊。

4. **開始共同作業工作階段**

    現在，只要**按一下**項目或叫用 「 共用 」 狀態列**Ctrl + Shift + P / Cmd + Shift + P** ，然後選取 「 即時共用：啟動共同作業工作階段 （共用） 」。

    ![共用按鈕](../media/vscode-share-button.png)

    > [!NOTE]
    > 您可能會要求您的桌面防火牆軟體所允許 Live Share 的代理程式在您共用的第一次開啟連接埠。 接受這完全是選擇性的但可讓受保護 「 直接模式 」 來改善效能，因為您正在使用的人員是在相同網路上時。 請參閱[變更連線模式](../reference/connectivity.md#changing-the-connection-mode)如需詳細資訊。

    邀情連結將會自動複製到剪貼簿。 開啟瀏覽器中，此連結可讓其他人加入新的共同作業工作階段與他們共用這些資料夾的內容。

    您也會看到 「 共用 」 狀態列項目轉換，來代表工作階段狀態。 請參閱[工作階段狀態](#session-states)下方資訊看起來像這樣。

    請注意，是否您需要取得邀請連結一次您已經開始共用之後, 您存取該工作階段狀態狀態列圖示上按一下並選取 [邀請其他人 （複製連結）]。

5. **[選用]啟用唯讀模式**

    一旦您開始您的共同作業工作階段，您可以設定為唯讀，以防止來賓對共用的程式碼進行編輯的工作階段。

    共用之後, 您會收到通知，邀情連結，已複製到剪貼簿。 然後，您可以選取的選項，讓工作階段，唯讀狀態。

    ![VS 程式碼為唯讀模式](../media/vscode-read-only-toast.png)

6. **將連結傳送給其他人**

    透過電子郵件、 Slack 傳送連結、 Skype 等，可與您想要邀請。 請注意，給定的層級存取 Live Share 工作階段可以提供給來賓**您應該只與您所信任之人員共用**和考慮透過您共用的影響。

    > **安全性秘訣：** 想要了解安全性含意，Live Share 功能嗎？ 請參閱[安全性](../reference/security.md)文章。

    如果您受邀來賓有問題，「[快速入門：加入您的第一個工作階段](../quickstart/join.md)」 文章上啟動並執行以來賓身分提供更多的資訊。

7. **[選用]核准客體**

    根據預設，客體將會自動加入您的共同作業工作階段，而且當他們準備好要與您合作，將會通知您。 雖然這個通知可讓您從工作階段中移除它們，您也可以選擇改為針對聯結的任何人都需要明確的 「 核准 」。

    若要啟用這項功能，只要將下列新增至 settings.json:

         "liveshare.guestApprovalRequired": true

    開啟此設定之後，通知會提示您核准的客體，才能夠加入。

    ![Visual Studio 程式碼加入核准要求](../media/vscode-join-approval.png)

    請參閱[邀請和聯結存取](../reference/security.md#invitations-and-join-access)邀請安全性考量的其他詳細資料。

就這麼簡單 ！

### <a name="stop-the-collaboration-session"></a>停止共同作業工作階段

為主機，您可以停止完全共用，並結束共同作業工作階段，隨時開啟 Live Share 檢視，在 總管 或 Live Share 自訂索引標籤，然後選取 停止共同作業工作階段 圖示。

![停止共同作業工作階段](../media/vscode-end-collaboration-viewlet.png)

將工作階段已結束，通知所有來賓。  一旦工作階段已結束，來賓將不再能夠存取內容和任何暫存檔案會自動清除。

有共用的問題嗎？ 請參閱[疑難排解](../troubleshooting.md#share-and-join)。

## <a name="join-a-collaboration-session"></a>加入共同作業工作階段

下載並安裝 Visual Studio Live Share 之後, 來賓只需要採取幾個步驟加入代管協同作業工作階段。 有兩種方式，加入：[透過瀏覽器](#join-via-the-browser)並[手動](#join-manually)。

> **安全性秘訣：** 為來賓加入共同作業工作階段，請務必了解主機可能會針對您的存取權限制至特定檔案或功能。 想要了解一些 Live Share 功能和設定的安全性含意？ 請參閱[安全性](../reference/security.md)文章。

### <a name="join-via-the-browser"></a>加入透過瀏覽器

加入共同作業工作階段的最簡單方式是直接在網頁瀏覽器中開啟邀情連結。 以下是您可以預期當您遵循此流程。

1. **登入**

    安裝 Live Share 延伸模組、 重新載入，並等待相依性，以完成安裝之後, 您會想要讓其他的共同作業者知道您的身分登入。 請參閱[登入](#sign-in)如需詳細資訊。

2. **按一下 [邀請] 連結/您的瀏覽器中開啟邀請**

    現在，只要開啟 （或重新開啟） 瀏覽器中的 [邀請] 連結。

    > **注意**：如果您尚未安裝 Live Share 延伸模組，您將會看到擴充功能市集的連結。 安裝擴充功能並重新啟動您的工具，然後重試。

    您應該會收到通知，瀏覽器就會想要啟動已啟用 Live Share 工具。 如果您讓它啟動您所選的工具，您會連接到其啟動之後的共同作業工作階段。

    ![加入頁面](../media/join-page.png)

    如果主機已離線，您會收到通知現在改為。 然後，您可以連絡主機，並要求他們再次共用。

    > [!NOTE]
    > 確定您已經**至少一次啟動此工具**之後安裝 Visual Studio Live Share 延伸模組，以及允許安裝完成之前開啟/重新 opening [邀請] 頁面。 仍然有問題嗎？ 請參閱[手動聯結](#join-manually)。

3. **共同作業**

    就這麼容易！ 稍後您將連接，您可以開始進行共同作業。

    您會看到 [共用] 按鈕轉換來傳遞 「 工作階段狀態 」。 請參閱[工作階段狀態](#session-states)下方資訊看起來像這樣。

    您將會自動進入完成聯結後，將目前正在編輯主機檔案。

### <a name="join-manually"></a>手動聯結

您可以手動加入不使用網頁瀏覽器，有助於在已經執行您想要使用此的工具的情況下，您想要使用不同的工具，您通常這樣做，或如果您遇到問題取得邀請連結至工作因為某些原因。 此程序很簡單：

1. **登入**

    安裝 Live Share 延伸模組、 重新載入，並等待相依性，以完成安裝之後, 您會想要讓其他的共同作業者知道您的身分登入。 請參閱[登入](#sign-in)如需詳細資訊。

2. **使用 [加入] 命令**

    在 VS Code 活動列中，開啟 [Live Share 自訂] 索引標籤，然後選取 「 聯結共同作業工作階段...」圖示或項目。

    ![聯結 viewlet 圖示](../media/vscode-join-viewlet.png)

3. **貼上 [邀請] 連結**

    若要確認輸入貼上您所傳送，並叫用邀請 URL。

4. **共同作業 ！**

    就這麼容易！ 您應該連接到共同作業工作階段會短暫。

    您會看到 [共用] 按鈕轉換來傳遞 「 工作階段狀態 」。 請參閱[工作階段狀態](#session-states)下方資訊看起來像這樣。

    您將會自動進入完成聯結後，將目前正在編輯主機檔案。

### <a name="leave-the-collaboration-session"></a>讓共同作業工作階段

為來賓，則可以將共同作業工作階段，而不需要結束它供其他人只要關閉 VS Code 視窗。 如果您想讓視窗保持開啟，您可以開啟即時共用總管檢視或 Live Share 自訂索引標籤，並選取 「 讓共同作業工作階段 」 的圖示。

![保留工作階段圖示](../media/vscode-leave-session-viewlet.png)

任何暫存檔案會自動清除因此不需要任何進一步的動作。

有問題的聯結嗎？ 請參閱[疑難排解](../troubleshooting.md#share-and-join)。

## <a name="co-editing"></a>共同編輯

客體已加入共同作業工作階段之後, 會立即能夠看到彼此的編輯和即時的選取項目所有的共同作業者。 您只需要是從 [檔案總管] 中挑選檔案，並開始編輯。 主機和來賓，當您讓它們，但可以參與簡單反覆查看並快速鎖定來縮小解決方案變得本身會看到的編輯。

> [!NOTE]
> 加入唯讀的共同作業工作階段，可防止來賓能夠對檔案進行編輯。 主機可以[啟用唯讀模式，當它們共用](#share-a-project)。 為來賓，您可以指示是否您已加入的唯讀工作階段來看看您[工作階段狀態](#session-states)。

![顯示共同編輯螢幕擷取畫面](../media/vscode-coedit.png)

> [!NOTE]
> 共同編輯有適用於特定語言的限制。 如需依語言列出功能的狀態，請參閱[平台支援](../reference/platform-support.md)。

超過資料指標和編輯，您的選取項目也會顯示該相同的檔案中的所有參與者。 這比較容易反白顯示問題，可能會存在，或傳達想法。

![顯示反白顯示螢幕擷取畫面](../media/vscode-highlight.png)

更棒的是，您和其他參與者可以瀏覽至共用專案中的任何檔案。 您可以編輯一起或分開這表示您可以順暢地切換進行小型的調整和完整共同編輯的調查。

產生的編輯會保存在主機電腦上儲存因此那里不需要同步處理、 推送或傳送檔案，一旦您完成編輯。 編輯為"只 there。"

> **安全性秘訣：** 指定的所有參與者都可以獨立地巡覽及編輯檔案，做為主機，您可能想要限制哪些檔案來賓都能透過在專案中存取。 vsls.json 檔案。 為來賓，也很重要要了解您可能不會看到這些設定後的特定檔案。 請參閱[控制檔案存取權和可見性](../reference/security.md#controlling-file-access-and-visibility)如需詳細資訊。

### <a name="changing-participant-flag-behaviors"></a>變更參與者的旗標的行為

根據預設，Visual Studio Live Share 自動旁邊會顯示 「 旗標 」 的參與者游標暫留時，或當他們編輯時，反白顯示，或移動其資料指標。 在某些情況下，您可能會想要變更此行為。

只要**編輯 settings.json** (檔案 > 喜好設定 > 設定) 新增下列行，其中，然後重新啟動 VS Code:

| 設定 | 行為 |
|---------|----------|
| ``"liveshare.nameTagVisibility":"Never"`` | 當您將游標暫留時，才看得到旗標。 |
| ``"liveshare.nameTagVisibility":"Activity"`` | 這是預設值。 旗標會暫留時顯示或如果參與者編輯時，會反白顯示，或將其指標。 |
| ``"liveshare.nameTagVisibility":"Always"`` | 旗標為永遠可見。 |

## <a name="following"></a>遵循

您有時需要說明橫跨多個檔案或程式碼中多個位置的問題和設計。 在這些情況下，它可用來暫時遵循同事，在整個專案中移動。 基於這個理由，當您加入共同作業工作階段時您要自動 「 遵循 」 主應用程式。 時遵循其他人，您的編輯器將維持其目前開啟的檔案和捲動位置同步。

> [!NOTE]
> 根據預設，Live Share 共用開啟外部共用資料夾的檔案。 如果您想要停用此功能，更新`liveshare.shareExternalFiles`Live 共用`false`settings.json 中。

若要開始追踨的參與者 （為主機或客體），按一下其即時共用總管檢視 或 自訂 索引標籤中的參與者的清單中的名稱。表示您已遵循它們將會填入其名稱旁邊的圓形。

![VS Code 遵循 viewlet](../media/vscode-follow-multiple-viewlet.png)

或者，您可以按一下 釘選圖示，在右上方的編輯器群組或按下**Ctrl + Alt + F / Cmd + Alt + F**。

![VS 程式碼 pin](../media/vscode-pin.png)

> [!NOTE]
> 如果多個其他人共同作業工作階段中，系統會要求您選取您想要遵循的參與者。
>
>![螢幕擷取畫面顯示的共同作業者清單](../media/vscode-list-collaborators.png)

因為下列繫結至編輯器群組，您可以使用分割檢視 （或格線版面配置 ！） 有如下的參與者的群組和不是群組。 這可讓您被動地遵循其他人也獨立工作項目時。 選取編輯器群組，您可以選取 [參與者] 清單中的參與者，必須遵循它們該群組。

![在分割檢視中的 VS 程式碼 pin](../media/vscode-follow-split.png)

若要讓您輕鬆地切換移出 「 遵循模式 」，並開始您自己的編輯，您會自動停止追踨這些事件發生時：

1. 您開始編輯目前作用中的檔案
1. 您可以開啟不同的檔案
1. 關閉目前作用中的檔案

此外，您可以明確地停止下列某人的再按一下 釘選圖示或按下**Ctrl + Alt + F / Cmd + Alt + F**。

## <a name="listing-participants"></a>列出參與者

若要查看誰是共同作業工作階段中的快速方法是查看即時共用總管檢視 或 自訂 索引標籤中的 參與者 清單。檢視會顯示您的工作階段中的所有參與者。

![螢幕擷取畫面顯示使用者狀態 列圖示](../media/vscode-explorer-view.png)

按一下此清單中的任何參與者都會隨著他們在使用中編輯器群組中。

或者，您可以叫用**Ctrl + Shift + P / Cmd + Shift + P** ，然後選取 「 即時共用：列出參與者 」 的命令或**按一下**上顯示的工作階段中的參與者數目之狀態列項目。

![螢幕擷取畫面顯示使用者狀態 列圖示](../media/vscode-user-status.png)

然後會出現在工作階段中的所有參與者的清單。 不同於按一下釘選圖示，即使只有一個其他人與您工作階段中以便您隨時可以看到其他人所在位置，會顯示此清單。 為了方便起見，釘選圖示，例如您接著可以挑選其中一個參與者從清單中，遵循它們。 如果您想要改為結束，請按 escape 鍵。

## <a name="focusing"></a>將焦點放

偶爾您可能需要每個人的共同作業工作階段，並看看您要執行的項目中。 即時共用可讓您詢問，每個人 」 著重 「 於您通知，讓他們可以輕鬆將隨著您一起傳回。

開啟 VS Code 活動列或即時共用總管] 檢視中，[Live Share 自訂索引標籤並選取 「 專注參與者 」 圖示。

![焦點 viewlet 圖示](../media/vscode-focus-viewlet.png)

一旦您執行命令時，共同作業工作階段中的每個人然後將會收到通知，您已要求其注意力。

![焦點快顯通知](../media/vscode-focus-toast.png)

它們也可以只按一下 [跟隨] 直接從通知當他們準備好要將其焦點放在您。

## <a name="co-debugging"></a>共同偵錯

Visual Studio Live Share 的共同作業的偵錯功能是功能強大且唯一的方式來偵錯問題。 之外啟用問題進行疑難排解的共同作業體驗，它也您和您能夠調查問題的工作階段中的其他參與者可能是環境特定藉由提供共用的偵錯工作階段主機的電腦上。

> **安全性秘訣：** 指定的所有參與者都可以獨立地巡覽及編輯檔案，做為主機，您可能想要限制哪些檔案來賓都能透過在專案中存取。 vsls.json 檔案。 您也應該要知道主控台/REPL 的存取權，就表示，因此您應該只共同進行偵錯與您信任的參與者可以執行您的電腦上命令。 為來賓，也很重要要了解您可能無法如它就會逐步執行特定的檔案限制檔案，這些設定後，請遵循偵錯工具。 請參閱[控制檔案存取權和可見性](../reference/security.md#controlling-file-access-and-visibility)如需詳細資訊。

使用簡單。

1. 請務必在主機和所有來賓有適當的偵錯擴充功能安裝。 （技術上來說這不一定有必要，但它通常是個不錯的主意）。

2. 為主機，如果尚未設定專案，您應該[設定 launch.json](https://code.visualstudio.com/Docs/editor/debugging#_launch-configurations)偵錯的應用程式，從 VS Code，可以用正常方式。 需要任何特殊的設定不。

3. 接下來，主應用程式可以開始偵錯使用如往常一樣偵錯 索引標籤中的按鈕。

    ![VS 程式碼偵錯 按鈕](../media/vscode-debug-button.png)

    > [!TIP]
    > 您也可以參與 Visual Studio 偵錯工作階段從 VS Code，反之亦然 ！ 請參閱[Visual Studio 指示](vs.md#co-debugging)共同偵錯，如需詳細資訊。

一旦主機端，附加偵錯工具，也會自動附加所有來賓。 一個偵錯 」 工作階段 」 的主機電腦上執行時，所有參與者都連接到它，並有自己的檢視。

![VS Code 偵錯工具附加](../media/vscode-debugger.png)

任何人都可以逐步執行偵錯的處理序，讓共同作業者，而不必交涉控制項之間順暢切換。

> [!NOTE]
> 如需依語言或平台列出偵錯功能的狀態，請參閱[平台支援](../reference/platform-support.md)。

每個共同作業者可以調查不同的變數、 直接跳到呼叫堆疊中的不同檔案、 檢查變數，並甚至新增或移除中斷點。 共同編輯功能，則會允許每個參與者雄辯來追蹤其他的提供獨特的功能，可順暢地切換同時調查問題的不同層面，並以共同作業方式偵錯的所在位置。

> [!NOTE]
> 在唯讀模式的共同作業工作階段中的來賓將無法逐步執行偵錯程序。 它們可以不過，還是新增或移除中斷點，並檢查變數。

![動畫的並行偵錯](../media/co-debug.gif)

### <a name="change-when-vs-code-joins-debugging-sessions"></a>變更當 VS Code 偵錯工作階段的聯結

根據預設，為來賓，您將會自動附加至偵錯工作階段主機的共用時。 不過，在某些情況下，您可能會發現這種行為造成干擾。 幸運的是，您可以將它變更，如下所示：

只要**編輯 settings.json** (檔案 > 喜好設定 > 設定) 新增下列行，其中，然後重新啟動 VS Code:

| 設定 | 行為 |
|---------|----------|
|``"liveshare.joinDebugSessionOption":"Automatic"`` | 預設值。 為來賓，您將會自動加入任何共用的偵錯工作階段，以啟動主機。 |
| ``"liveshare.joinDebugSessionOption":"Prompt"`` | 為來賓，系統會提示您是否要加入共用的偵錯工作階段，以啟動主機時。 |
| ``"liveshare.joinDebugSessionOption":"Manual"`` | 為來賓，您必須手動將任何偵錯工作階段。 請參閱[卸離及重新附加](#detaching-and-reattaching)。 |

### <a name="detaching-and-reattaching"></a>卸離及重新附加

為來賓，您可能想要停止暫時偵錯。 幸運的是，您可以只按一下要中斷連結偵錯工具，而不會影響主機或其他來賓的偵錯 工具列的 停止 圖示。

![VS Code 偵錯工具停止按鈕](../media/vscode-debug-stop.png)

如果您已更新的設定，因此您不會再自動附加，或如果您只想要稍後再重新附加，則可以藉由按下**Ctrl + Shift + P / Cmd + Shift + P**或是**按一下**上的工作階段狀態狀態列項目和選取 「 附加至共用偵錯工作階段 」。

![VS Code 附加偵錯工具](../media/vscode-reattach.png)

### <a name="sharing-the-running-application-in-a-browser"></a>共用瀏覽器中執行的應用程式

Visual Studio 程式碼並沒有已知 「 web 應用程式連接埠 」 如 Visual Studio 專案類型，例如 ASP.NET 的概念。 不過，如果您要聯結的共同作業工作階段，從 Visual Studio 主應用程式，您可能會自動看到預設瀏覽器偵錯也就是，則會自動連線到主機的執行中應用程式啟動時，會出現。 請參閱[Visual Studio 功能](vs.md#automatic-web-app-sharing)如需詳細資訊。

為主機，您可以藉由手動共用應用程式或其他端點，例如使用 「 共用的本機伺服器 」 功能的 RESTful 服務達到類似的項目。 Visual Studio 和 VS Code 的來賓，就可以開啟瀏覽器以查看執行中應用程式相同的 localhost 連接埠。  請參閱[共用伺服器](#share-a-server)如需詳細資訊。

## <a name="share-a-server"></a>共用伺服器

有時，作為共同作業工作階段主機，您可能會發現您想要共用的 web 應用程式或其他在本機執行來賓的伺服器或服務。 這可以介於資料庫和其他伺服器的其他 RESTful 端點。 Visual Studio Live Share 可讓您指定的本機連接埠號碼，選擇性地指定的名稱，然後將它分享所有來賓。

來賓則是能夠存取您共用該連接埠從自己的本機電腦上完全相同的連接埠的伺服器。 比方說，如果您共用的 web 伺服器**執行連接埠 3000**，客體會可以存取該相同的執行網頁伺服器上其**自己的機器**在 http://localhost:3000！ 這是透過在主機與客體之間的 SSH 或 SSL 安全通道來完成，並透過服務進行驗證，因此您可以確定只在共同作業工作階段中可以存取。

> **安全性秘訣：** 為主機，您應該謹慎選擇與您分享來賓，並停在某應用程式連接埠 （而非共用系統連接埠） 的連接埠。 來賓，共用的連接埠的行為如同就好似他們自己的機器上執行，伺服器/服務。 這是非常實用，但如果共用錯誤的連接埠，可能也會有風險。

基於安全考量，您指定的連接埠上執行的伺服器只可用於其他來賓。 幸運的是，就可以輕鬆地新增為共同作業的工作階段的其中一個**主機**。 方式如下：

1. 開啟 VS Code 活動列或即時共用總管] 檢視中，[Live Share 自訂索引標籤，然後選取 [共用伺服器...]項目，或按一下圖示。

    ![VS 程式碼共用本機伺服器](../media/vscode-share-local-server-viewlet.png)<br />

1. 輸入在伺服器執行的連接埠號碼和選擇性名稱。

    ![連接埠號碼的提示字元的螢幕擷取畫面](../media/vscode-enter-port.png)<br />

就這麼容易！ 現在將會將您所指定的連接埠上的伺服器對應至相同的連接埠上的每個客體的 localhost，（除非該連接埠已被佔用） ！

如果連接埠已在客體機器上的使用中，會自動選取另一個。 幸運的是，為來賓，您所見目前共用的連接埠的清單 （依名稱指定） 即時共用總管檢視 或 VS Code 活動列中，在共用的伺服器 清單下尋找自訂索引標籤中。 選取的項目，則會在您的瀏覽器中開啟該伺服器。 您也可以以滑鼠右鍵按一下並選取選項來將連結複製到剪貼簿的伺服器。

![VS 程式碼存取本機伺服器](../media/vscode-access-shared-server-viewlet.png)<br />

請注意，*來賓無法*控制主機的電腦上的連接埠共用基於安全性考量。

若要**停止**共用與主機的本機伺服器，停留在 即時共用總管檢視或自訂的索引標籤上，共用的伺服器清單中的伺服器項目，然後按一下 「 取消共用伺服器 」 圖示。

![VS 程式碼停止共用伺服器](../media/vscode-stop-sharing-server-viewlet.png)<br />

## <a name="share-a-terminal"></a>共用終端機

新式開發經常會運用各種命令列工具。 幸運的是，Live Share 可讓您為主機，來賓 「 分享終端機 」 （選擇性）。 共用終端機可以是唯讀或完整的共同作業，因此您和來賓可執行命令，並查看結果。 您可以為終端機輸出中的來賓可見性，或讓他們取得實際操作和執行測試、 組建或您的電腦，才會發生的平均分級環境特定問題。

不過，終端機都**不**共用預設情況下，因為它們可讓來賓至少是唯讀存取您所執行的命令 （如果不執行命令本身的能力） 的輸出。 實際上，如此一來，您可以自由在沒有危險的本機終端機中執行命令，並只共用時需要執行這項操作。 此外，只有主機就可以開始共用的終端機，以防止從一個啟動和執行您不預期或監看的來賓。

為主機，您可以共用終端機，VS Code 活動列或即時分享的總管檢視中，開啟即時分享的自訂索引標籤，然後選取 [共用伺服器...]項目，或按一下圖示。

![VS Code 共用終端機](../media/vscode-share-terminal-viewlet.png)<br />

此時，您可以選取唯讀或讀取/寫入終端機從功能表。 讀取/寫入終端機中時，每個人都可以輸入在終端機中包括容易介入如果來賓所執行的動作不喜歡的主機。 不過，為了安全起見，應該**只提供讀取/寫入存取權的來賓，當您知道它們有實際需要**後固定使用唯讀模式的終端機中，如案例中，您只是來賓，請參閱您執行任何命令的輸出。

> [!NOTE]
> 如果共同作業工作階段處於唯讀模式，唯讀的終端機可以共用主機。

![唯讀或讀取/寫入選取項目](../media/vscode-share-terminal-ro-rw.png)<br />

一旦您已選取您想要啟動的共用終端機的種類，新的共用終端機會出現在 VS Code 終端機 索引標籤中。

![共用的終端機執行](../media/vscode-share-terminal-up.png)<br />

如果共用的多個終端機，或您的焦點是在不同的索引標籤中，您可以將焦點移至特定的終端機所共用的終端機清單中選取項目。

![共用終端機將焦點移](../media/vscode-shared-terminal-focus.png)<br />

若要結束您的終端機工作階段，只要輸入結束、 關閉終端機視窗中，或按一下 「 取消共用終端機 」 中的圖示即時共用總管檢視或自訂索引標籤，而每個人都將會中斷。

## <a name="session-states"></a>工作階段狀態

您已經啟動，或加入共同作業工作階段，並且有存取共用的內容之後，Visual Studio Live Share 狀態列項目就會更新其外觀，以反映的使用中的共同作業工作階段狀態。

您通常會看到狀態如下：

| 狀況 | 狀態列 | 描述 |
|-------|--------------------|-------------|
| 非使用中 | ![VS 程式碼狀態： 非使用中](../media/vscode-status-share.png) | 沒有任何作用中的共同作業工作階段並不會共用。 |
| 主機:共用進行中 | ![VS 程式碼狀態： 正在共用](../media/vscode-status-sharing.png)| 正在啟動共同作業工作階段，並設定共用的內容就會開始。 |
| 主機:共用 | ![VS 程式碼狀態： 共用使用中 ](../media/vscode-status-active.png)| 共同作業工作階段已啟動，並在共用內容。 |
| 主機:共用唯讀 | ![VS 程式碼狀態： 共用唯讀](../media/vscode-status-sharing-read-only.png)| 共用的唯讀狀態的共同作業工作階段。 |
| 來賓︰加入工作階段 | ![VS 程式碼狀態： 聯結](../media/vscode-status-joining.png)| 加入現有的共同作業工作階段。 |
| 來賓︰已加入 | ![VS 程式碼狀態： 已加入](../media/vscode-status-active.png) | 加入並連接至使用中的共同作業工作階段和接收的共用的內容。 |
| 來賓︰已加入唯讀模式 | ![VS 程式碼狀態： 已加入唯讀模式](../media/vscode-status-joined-read-only.png) | 加入並連接到作用中的唯讀共同作業工作階段。 |

## <a name="guest-limitations"></a>來賓限制

雖然目前沒有來賓會在使用上面所述的功能時遇到的一些缺點，共同作業工作階段主機會保留其選擇的工具的完整功能。 如需詳細資訊，請參閱下列主題：

- [語言和平台支援](../reference/platform-support.md)
- [延伸模組支援](../reference/extensions.md)
- [所有主要 bug、 功能要求和限制](https://aka.ms/vsls-issues)
- [所有的功能要求和限制](https://aka.ms/vsls-feature-requests)
- [疑難排解](../troubleshooting.md)

## <a name="next-steps"></a>後續步驟

看看這些額外的文章，如需詳細資訊。

- [快速入門：共用您的第一個專案](../quickstart/share.md)
- [快速入門：加入您的第一個工作階段](../quickstart/share.md)
- [操作說明：使用 Visual Studio 進行共同作業](vs.md)
- [Live Share 的連線需求](../reference/connectivity.md)
- [Live Share 的安全性功能](../reference/security.md)
- [Linux 安裝詳細資料](../reference/linux.md)

有問題嗎？ 請參閱[疑難排解](../troubleshooting.md)或[提供意見反應](../support.md)。
