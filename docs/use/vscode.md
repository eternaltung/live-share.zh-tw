---
title: 使用 Visual Studio Code 共同作業 - Visual Studio Live Share | Microsoft Docs
description: 適用於 Visual Studio Code 和 Live Share 的一組共同作業操作說明。
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
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2019
ms.locfileid: "57255557"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="how-to-collaborate-using-visual-studio-code"></a>操作說明：使用 Visual Studio Code 共同作業

準備好在 VS Code 中使用 Live Share 進行共同作業了嗎？  如果是，您來對地方了！ 在本文中，我們將逐步引導您了解如何使用適用於 Visual Studio Code 的 Visual Studio Live Share 擴充的特定功能。

請注意，這裡所描述的所有共同作業活動，都會涉及單一**共同作業工作階段主持人**，以及一或多個**來賓**。 主持人是啟動共同作業工作階段的人員，而來賓是加入的任何人。

*在尋找簡易摘要嗎？請改為參閱[共用](../quickstart/share.md)或[加入](../quickstart/join.md)快速入門。*

> [!TIP]
> 您知道您可以「加入自己的共同作業工作階段」嗎？ 這讓您可以自行試用 Live Share，或是啟動 Visual Studio 或 VS Code 的執行個體，並從遠端連線到該執行個體！ 您甚至可以在這兩個執行個體使用相同的身分識別。 趕緊去瞧一瞧！

## <a name="installation"></a>安裝

開始之前，您必須確定已安裝符合 Live Share 核心需求的 Visual Studio Code 版本。 您需要在下列平台上執行的 **Visual Studio Code (1.22.0 或更高版本)**：

- **Windows**：7、8.1 或 10

- **macOS**：僅限 Sierra (10.12) 和更高版本。
    - 「因 [.NET Core 2.0 需求](https://go.microsoft.com/fwlink/?linkid=872315)，目前不支援 El Capitan (10.11) 和更低版本。」

- **Linux**：64 位元的 Ubuntu Desktop 16.04+、Fedora Workstation 27+、CentOS 7

    - 系統可能會提示您安裝 Live Share 要求的數個 [Linux 必要條件](#linux-install-steps)。
    - 「因 [.NET Core 2.0 需求](https://go.microsoft.com/fwlink/?linkid=872314)，目前不支援 32 位元的 Linux。」
    - 目前也不支援 ARM。
    - 請參閱 [Linux 安裝詳細資料](../reference/linux.md)一文，以取得使用下游及其他散發套件的詳細資料。

之後就能輕鬆下載並安裝 Visual Studio Live Share 延伸模組：

1. 安裝 <a href="https://code.visualstudio.com/">Visual Studio Code</a> \(英文\)
2. 從 Marketplace [下載](https://aka.ms/vsls-dl/vscode) \(英文\) 並安裝 Visual Studio Live Share 擴充。
3. 重新載入 Visual Studio Code
4. 等候相依性完成下載和安裝 (查看狀態列)。<br/>
    ![完成安裝](../media/vscode-finishing-install.png)
5. **Linux**：如果您看見有關安裝遺失程式庫的通知：
    1. 按一下通知中的 [安裝]。
    2. 收到提示時，輸入您的系統管理員 (sudo) 密碼。
    3. 於完成時重新啟動 VS Code。

下載並使用 Visual Studio Live Share 即表示您同意[授權條款](https://aka.ms/vsls-license)和[隱私權聲明](https://www.microsoft.com/en-us/privacystatement/EnterpriseDev/default.aspx)。 如果您遇到問題，請參閱[疑難排解](../troubleshooting.md)。

[![下載](../media/download.png)](https://aka.ms/vsls-dl/vscode) \(英文\)

### <a name="linux-install-steps"></a>Linux 安裝步驟

Linux 環境彼此之間很容易具有高度差異，其為數眾多的桌面環境和散發套件，很可能會使作業變得複雜。 不過，如果您維持使用 **Ubuntu Desktop** (16.04+)、**Fedora Workstation** (27+) 或 **CentOS 7**，且僅使用 **VS Code 的官方散發套件**，整個流程應該不會有任何變數。 不過，在使用非標準設定或下游散發套件的情況下，您便有可能會遇到問題。 請參閱 [Linux 安裝詳細資料](../reference/linux.md)以取得詳細資訊。

#### <a name="install-linux-prerequisites"></a>安裝 Linux 必要條件

某些 Linux 散發套件並沒有 Live Share 運作所需的程式庫。 根據預設，Live Share 會嘗試偵測並為您安裝 Linux 必要條件。 當 Live Share 遇到可能源自遺失程式庫的問題時，便會向您顯示快顯通知並要求安裝它們的權限。

![顯示 Linux 必要條件遺失之訊息的快顯通知](../media/vscode-linux-prereq-missing.png)

當您按一下 [安裝] 時，將會出現終端機視窗，且您必須在其中輸入系統管理員 (sudo) 密碼以繼續。 當此作業成功完成之後，請重新啟動 Visual Studio Code，一切便能就緒！ 您也應該查看**[依散發套件分類的提示](../reference/linux.md#tips-by-distribution)**，以查看其他提示和現有的因應措施。

如果您看見指令碼不支援散發套件的訊息，請參閱**[適用於社群支援散發套件的提示](../reference/linux.md#tips-for-community-supported-distros)** 以取得社群已和我們分享的相關資訊。

如果您**不想讓 VS Code 為您執行命令**，您也可以從終端機視窗執行下列命令，以隨時手動選擇重新執行此指令碼的最新版本：

    wget -O ~/vsls-reqs https://aka.ms/vsls-linux-prereq-script && chmod +x ~/vsls-reqs && ~/vsls-reqs

#### <a name="linux-browser-integration"></a>Linux 瀏覽器整合

Visual Studio Live Share 通常**不需要額外安裝步驟**以在 Linux 上啟用瀏覽器整合。

雖然此情況並不常見，但在某些散發套件上**系統可能會通知您需要系統管理員 (sudo) 密碼**才能完成安裝程序。 系統將會顯示終端機視窗，向您告知瀏覽器啟動器的安裝位置。 請在收到提示時直接輸入您的密碼，然後在安裝完成時按 Enter 以關閉終端機視窗。

您可以在**[這裡](../reference/linux.md#linux-browser-integration)** 深入了解此要求背後的原因，以及 Live Share 放置檔案的位置。 請注意，即使您無法順利使瀏覽器整合運作，您仍然可以**[手動加入共同作業工作階段](../use/vscode.md#join-manually)**。

## <a name="sign-in"></a>登入

若要進行共同作業，您需要登入 Visual Studio Live Share，以便使所有人知道您的身分。 這只是安全性措施，且**不會**將您加入任何行銷或其他研究活動。 您可以使用 Microsoft 個人帳戶 (例如 @outlook.com)、Microsoft 支援的公司或學校帳戶 (AAD)，或是 GitHub 帳戶。 登入很簡單。

請**按一下** [共用] 狀態列項目，或按 **Ctrl+Shift+P / Cmd+Shift+P** 並選取 [Live Share:使用瀏覽器登入] 命令。

![VS Code [登入] 按鈕](../media/vscode-sign-in-button.png)

系統將會顯示通知，要求您使用網頁瀏覽器登入。 按一下 [啟動登入] 將會開啟瀏覽器，以供您用來完成登入程序。 完成後，請直接關閉瀏覽器。

![要求使用網頁瀏覽器登入的快顯通知](../media/vscode-sign-in-toast.png)

> **Linux 使用者：** 如果您使用舊版 Live Share (v0.3.295 或更舊版本)，系統可能會提示您輸入使用者程式碼。 將延伸模組更新為最新版本，或在登入後按一下 [遇到問題了嗎?] 連結以查看程式碼。 請參閱[下方以取得詳細資料](#sign-in-using-a-user-code)。

在您於瀏覽器中完成登入程序後，如果 Visual Studio Code 並沒有偵測到您的登入，請參閱[使用使用者程式碼登入](#sign-in-using-a-user-code)。 否則，請參閱[疑難排解](../troubleshooting.md#sign-in)以取得其他提示。

### <a name="sign-in-using-a-user-code"></a>使用使用者程式碼登入

如果您遇到 VS Code 沒有偵測到已完成登入的問題，則可以改為輸入「使用者程式碼」。

1. 按 **Ctrl+Shift+P / Cmd+Shift+P** 並執行 [Live Share:使用使用者程式碼登入] 命令。

2. 系統應該會顯示瀏覽器，以供您用來完成登入程序。

    > [!NOTE]
    > 如果未自動出現瀏覽器，請在瀏覽器中開啟[這個位置](https://insiders.liveshare.vsengsaas.visualstudio.com/auth/login) \(英文\) 並登入。

3. 完成之後，請按一下 有任何問題嗎? 按一下這裡以取得使用者程式碼指示 以查看使用者程式碼。

    ![瀏覽器中使用者程式碼的圖片](../media/vscode-user-code-browser.png)

4. 複製使用者程式碼。

5. 最後，將使用者程式碼貼到執行命令後所出現的輸入欄位中，然後按 Enter 以完成登入程序。

    ![使用者程式碼輸入欄位的圖片](../media/vscode-user-code.png)

## <a name="using-the-live-share-viewlet"></a>使用 Live Share viewlet

安裝 Visual Studio Live Share 之後，系統會將自訂索引標籤新增至 VS Code 活動列上。 在此索引標籤中，您可以存取所有的 Live Share 功能以進行共同作業。 此外，當您共用或加入共同作業工作階段時，[總管] 索引標籤中也會出現檢視，以供您存取所有這些功能。

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-custom-tab.png" width="100%" alt="Live Share custom tab" />
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-explorer-view.png" width="100%" alt="Live Share explorer view"
</tr>
</table>

透過這些檢視，您便可以查看參與者在共用程式碼中所在的位置、按一下參與者以追蹤他們、聚焦在參與者身上、存取共用的伺服器和終端機等。

## <a name="using-the-scoped-command-menu"></a>使用範圍命令功能表

此外，所有的 Visual Studio Live Share 功能都可以從 Visual Studio Code 的 [命令選擇區] 中取得，您可以按 Ctrl+Shift+P / Cmd+Shift+P 或 F1 來存取 [命令選擇區]。 您可以輸入 "live share" 來取得命令的完整清單。

由於此清單可能很長，您應該運用狀態列所提供的範圍命令功能表。 按一下狀態列上的登入/工作階段狀態圖示，將會立即顯示可供您使用之命令的內容相關清單。

![VS Code 工作階段狀態圖示](../media/vscode-share-state.png)

## <a name="share-a-project"></a>共用專案

下載並安裝 Visual Studio Live Share 之後，請遵循這些步驟來啟動共同作業工作階段，並邀請同事與您合作。

1. **登入**

    安裝 Live Share 擴充，重新載入，並等待相依性完成安裝之後，您應該登入以便使其他共同作業者知道您的身分。 請參閱[登入](#sign-in)以取得詳細資料。

2. **開啟資料夾**

    使用您的一般工作流程來開啟您希望與來賓共用的資料夾、專案或方案。

3. **[選擇性] 更新隱藏或排除的檔案**

    根據預設，Live Share 會向來賓**隱藏**您共用資料夾中 .gitignore 檔案所參考的任何檔案/資料夾。 [隱藏] 檔案可防止該檔案在來賓的檔案樹狀目錄中顯示。 [排除] 檔案會套用更嚴格的規則，以防止 Live Share 在您前往定義，或在偵錯中或「受到跟隨」時進入檔案等情況下，為來賓開啟該檔案。 如果您希望隱藏/排除不同的檔案，您可以使用這些設定將 **.vsls.json** 檔案新增至您的專案。 請參閱[控制檔案存取權和可見性](../reference/security.md#controlling-file-access-and-visibility)以取得詳細資料。

4. **開始共同作業工作階段**

    現在，請**按一下** [共用] 狀態列項目，或按 **Ctrl+Shift+P / Cmd+Shift+P** 並選取 [Live Share:開始共同作業工作階段 (共用)]。

    ![[共用] 按鈕](../media/vscode-share-button.png)

    > [!NOTE]
    > 在您第一次共用時，桌面防火牆軟體可能會要求您允許 Live Share 代理程式開啟連接埠。 這完全是選擇性的，但它能提供安全的「直接模式」，以在您與一起工作的人員位於相同網路的情況下改善效能。 請參閱[變更連線模式](../reference/connectivity.md#changing-the-connection-mode)以取得詳細資料。

    邀請連結將會自動複製到剪貼簿。 在瀏覽器中開啟時，此連結可讓其他人加入新的共同作業工作階段，並與他們共用這些資料夾的內容。

    您也會看見 [共用] 狀態列的項目轉換，以代表工作階段狀態。 請參閱下面的[工作階段狀態](#session-states)資訊以了解其外觀。

    請注意，如果您要在啟動共用之後再次取得邀請連結，您可以按一下工作階段狀態列圖示並選取 [邀請其他人 (複製連結)] 來再次存取它。

5. **[選擇性] 啟用唯讀模式**

    一旦您啟動共同作業工作階段，您可以將工作階段設定為唯讀，以防止來賓對正在共用的程式碼進行編輯。

    共用之後，您會收到通知指出邀請連結已複製到剪貼簿。 您隨即可以選取選項來將工作階段設為唯讀。

    ![VS Code 唯讀模式](../media/vscode-read-only-toast.png)

6. **將連結傳送給某人**

    透過電子郵件、Slack、Skype 等將連結傳送給您希望邀請的人員。 請注意，考慮到 Live Share 工作階段所能為來賓提供的存取層級，**您應該只與您信任的人共用**，並考量共用這些內容的影響。

    > **安全性提示：** 想要了解 Live Share 功能的一些安全性影響嗎？ 請參閱[安全性](../reference/security.md)一文。

    如果您邀請的來賓有問題，《[快速入門：加入您的第一個工作階段](../quickstart/join.md)》一文提供以來賓身分啟動並執行的詳細資訊。

7. **[選擇性] 核准來賓**

    根據預設，來賓會自動加入您的共同作業工作階段，當他們準備好要與您共同作業時，您會收到通知。 雖然此通知提供您將他們從工作階段移除的選項，但您也可以選擇改為要求加入的任何人都需要獲得明確的「核准」。

    若要啟用這個功能，請直接將下列內容新增至 settings.json：

         "liveshare.guestApprovalRequired": true

    一旦您開啟此設定，系統會通知您進行核准，來賓才能加入。

    ![Visual Studio Code 加入核准要求](../media/vscode-join-approval.png)

    請參閱[邀請和加入存取權](../reference/security.md#invitations-and-join-access)以取得邀請安全性考量的其他詳細資料。

就這麼容易！

### <a name="stop-the-collaboration-session"></a>停止共同作業工作階段

身為主持人，您可以隨時完全停止共用並結束共同作業工作階段，方法是開啟 [總管] 中的 [Live Share] 檢視或 [Live Share] 自訂索引標籤，然後選取 [停止共同作業工作階段] 圖示。

![停止共同作業工作階段](../media/vscode-end-collaboration-viewlet.png)

系統會通知所有來賓工作階段已經結束。  工作階段結束之後，來賓將不再能夠存取內容，且系統會清除任何暫存檔。

有共用的問題嗎？ 請參閱[疑難排解](../troubleshooting.md#share-and-join)。

## <a name="join-a-collaboration-session"></a>加入共同作業工作階段

下載並安裝 Visual Studio Live Share 之後，來賓只需要幾個步驟就能加入主持人主持的共同作業工作階段。 有兩種方式可以加入：[透過瀏覽器](#join-via-the-browser)和[手動](#join-manually)。

> **安全性提示：** 作為來賓加入共同作業工作階段時，請務必了解主持人可能會限制您存取特定檔案或功能。 想要了解 Live Share 功能和設定的一些安全性影響嗎？ 請參閱[安全性](../reference/security.md)一文。

### <a name="join-via-the-browser"></a>透過瀏覽器加入

加入共同作業工作階段最簡單的方式，是在網頁瀏覽器中直接開啟邀請連結。 當您遵循此流程時，預期的情況如下。

1. **登入**

    安裝 Live Share 擴充，重新載入，並等待相依性完成安裝之後，您應該登入以便使其他共同作業者知道您的身分。 請參閱[登入](#sign-in)以取得詳細資料。

2. **按一下邀請連結/在您的瀏覽器中開啟邀請**

    現在，請在瀏覽器中開啟 (或重新開啟) 邀請連結。

    > **注意**：如果您尚未安裝 Live Share 擴充，您將會看到擴充市集的連結。 安裝擴充並重新啟動您的工具，然後重試。

    您應該會收到通知，指出瀏覽器想要啟動提供 Live Share 的工具。 如果您讓其啟動所選的工具，則在啟動後您將連線至共同作業工作階段。

    ![加入頁面](../media/join-page.png)

    如果主持人已離線，則會改為在此時收到通知。 您即可以連絡主持人，並要求再次共用。

    > [!NOTE]
    > 請務必在安裝 Visual Studio Live Share 擴充後**至少啟動工具一次**並允許安裝完成，再開啟/重新開啟邀請頁面。 仍然遇到問題嗎？ 請參閱[手動加入](#join-manually)。

3. **共同作業**

    就這麼容易！ 稍後會建立連線，您就可以開始共同作業。

    您將會看到 [共用] 按鈕發生轉換以表示「工作階段狀態」。 請參閱下面的[工作階段狀態](#session-states)資訊以了解其外觀。

    完成加入之後，系統會自動帶您到主持人目前在編輯的檔案。

### <a name="join-manually"></a>手動加入

您也可以手動加入，而不使用網頁瀏覽器。此方式在下列情況可能很有用：您想要使用的工具已經在執行、您想要使用其他工具而非平常使用的工具，或您可能因某些原因而無法取得邀請連結。 流程很簡單：

1. **登入**

    安裝 Live Share 擴充，重新載入，並等待相依性完成安裝之後，您應該登入以便使其他共同作業者知道您的身分。 請參閱[登入](#sign-in)以取得詳細資料。

2. **使用加入命令**

    開啟 VS Code 活動列中的 [Live Share] 自訂索引標籤，然後選取 [加入共同作業工作階段] 圖示或重試。

    ![加入 viewlet 圖示](../media/vscode-join-viewlet.png)

3. **貼上邀請連結**

    貼上您收到的邀請 URL 並按 Enter 以確認。

4. **共同作業！**

    就這麼容易！ 您應該很快就會連線到共同作業工作階段。

    您將會看到 [共用] 按鈕發生轉換以表示「工作階段狀態」。 請參閱下面的[工作階段狀態](#session-states)資訊以了解其外觀。

    完成加入之後，系統會自動帶您到主持人目前在編輯的檔案。

### <a name="leave-the-collaboration-session"></a>離開共同作業工作階段

身為來賓，您可以直接關閉 VS Code 視窗來離開共同作業工作階段，而不會結束其他人的作業。 如果您想讓視窗保持開啟，則可以開啟 Live Share [總管] 檢視或 [Live Share] 自訂索引標籤，並選取 [離開共同作業工作階段] 圖示。

![離開工作階段圖示](../media/vscode-leave-session-viewlet.png)

系統會自動清除任何暫存檔，所以您無須採取進一步動作。

有加入的問題嗎？ 請參閱[疑難排解](../troubleshooting.md#share-and-join)。

## <a name="co-editing"></a>共同編輯

來賓加入共同作業工作階段之後，所有共同作業者都能立刻即時地看到其他人所編輯和選取的項目。 您只需要從 [檔案總管] 中挑選檔案並開始編輯。 當您在編輯時，主持人和來賓都能查看，並且能親自參與，使逐一查看變得簡單，而且很快就能找出解決方案。

> [!NOTE]
> 加入唯讀共同作業工作階段會防止來賓對檔案進行編輯。 主持人可以[在共用時啟用唯讀模式](#share-a-project)。 身為來賓，您可以查看您的[工作階段狀態](#session-states)，以分辨您是否已加入唯讀工作階段。

![顯示共同編輯的螢幕擷取畫面](../media/vscode-coedit.png)

> [!NOTE]
> 對於特定語言，共同編輯有一些限制。 如需依語言列出功能的狀態，請參閱[平台支援](../reference/platform-support.md)。

除了游標和編輯之外，在相同檔案中的參與者也能看到您所選取的項目。 這可以讓您輕鬆反白顯示問題的可能位置或傳達想法。

![顯示反白顯示的螢幕擷取畫面](../media/vscode-highlight.png)

更棒的是，您和其他參與者可以瀏覽至共用專案中的任何檔案。 你們可以一起或獨立地編輯，這表示您可以流暢地在進行調查、做出小型調整，以及採取完全共同作業編輯之間進行切換。

編輯的結果會於儲存時保留在主持人的機器上，因此當您完成編輯時，不需要互相同步、推送或傳送檔案。 您所做的編輯都會「直接保留」。

> **安全性提示：** 由於所有參與者都能獨立地瀏覽和編輯檔案，身為主持人的您可能會想要使用 .vsls.json 檔案來限制來賓可存取您專案中的哪些檔案。 身為來賓，請務必了解到因為這些設定，您可能不會看到特定檔案。 請參閱[控制檔案存取權和可見性](../reference/security.md#controlling-file-access-and-visibility)以取得詳細資料。

### <a name="changing-participant-flag-behaviors"></a>變更參與者旗標行為

根據預設，Visual Studio Live Share 會自動在參與者暫留其游標、進行編輯或反白顯示，或是移動其游標時，在游標旁邊顯示「旗標」。 在某些情況下，您可能會想要變更此行為。

請直接**編輯 settings.json** ([檔案] > [喜好設定] > [設定])，新增下列其中一行，然後重新啟動 VS Code：

| 設定 | 行為 |
|---------|----------|
| ``"liveshare.nameTagVisibility":"Never"`` | 旗標只會在您將游標暫留時才可見。 |
| ``"liveshare.nameTagVisibility":"Activity"`` | 這是預設值。 旗標會在游標暫留期間，或在參與者進行編輯或反白顯示，或是移動其指標時才可見。 |
| ``"liveshare.nameTagVisibility":"Always"`` | 旗標一律可見。 |

## <a name="following"></a>追蹤

您有時需要說明橫跨多個檔案或程式碼中多個位置的問題和設計。 在這些情況下，暫時追蹤同事在專案中的動作可能會很有用。 因此，當您加入共同作業工作階段時，您會自動「追蹤」主持人。 在追蹤某人時，您的編輯器會與他們目前開啟的檔案和捲動位置保持同步。

> [!NOTE]
> 根據預設，Live Share 也會共用位於已共用資料夾外的檔案。 如果您想要停用此功能，請在 settings.json 中將 `liveshare.shareExternalFiles` Live Share 更新為 `false`。

若要開始追蹤參與者 (無論是以主持人或來賓的身分)，請在 Live Share [總管] 檢視或自訂索引標籤中的參與者清單中按一下他們的名稱。其名稱旁邊的圓形將會填滿，以指出您正在追蹤他們。

![VS Code 從 viewlet 追蹤](../media/vscode-follow-multiple-viewlet.png)

或者，您可以按一下編輯器群組右上角的圖釘圖示，或按 **Ctrl+Alt+F / Cmd+Alt+F**。

![VS Code 圖釘](../media/vscode-pin.png)

> [!NOTE]
> 如果有多個其他人位於共同作業工作階段中，系統將會詢問您要追蹤哪一個參與者。
>
>![顯示共同作業者清單的螢幕擷取畫面](../media/vscode-list-collaborators.png)

由於追蹤是繫結至編輯者群組，您可以使用分割檢視 (或是格線配置！) 來建立會追蹤某個參與者的群組，以及另一個不會追蹤該參與者的群組。 這可讓您在被動地追蹤某個人的情況下，同時個別處理其他工作。 在選取編輯者群組時，您可以從參與者清單中選取某個參與者，來讓該群組追蹤他們。

![VS Code 分割檢視中的圖釘](../media/vscode-follow-split.png)

為了方便切換離開「追蹤模式」並開始自行編輯，如果發生下列情況，您就會自動停止追蹤：

1. 您開始編輯目前的作用中檔案
1. 您開啟其他檔案
1. 您關閉目前的作用中檔案

此外，您可以再次按一下圖釘圖示，或按 **Ctrl+Alt+F / Cmd+Alt+F**來明確地停止追蹤某人。

## <a name="listing-participants"></a>列出參與者

查看共同作業工作階段中有誰的快速方式，就是查看 Live Share [總管] 檢視或自訂索引標籤中的參與者清單。該檢視將會顯示您工作階段中的所有參與者。

![顯示使用者狀態列圖示的螢幕擷取畫面](../media/vscode-explorer-view.png)

按一下清單中的任何參與者，將會在您的作用中編輯器群組中追蹤他們。

或者，您可以按 **Ctrl+Shift+P / Cmd+Shift+P** 並選取 [Live Share:列出參與者] 命令，或**按一下**顯示工作階段中參與者數目的狀態列項目。

![顯示使用者狀態列圖示的螢幕擷取畫面](../media/vscode-user-status.png)

系統將會顯示工作階段中所有參與者的清單。 和按一下圖釘圖示不同，就算工作階段中除了您以外只有另一個人員，此清單仍然會顯示，讓您隨時都可以快速地查看其他人所在的位置。 為了方便起見，和圖釘圖示一樣，您接著可以從清單中選擇其中一個參與者來追蹤他們。 如果您想要改為結束，請按 ESC。

## <a name="focusing"></a>聚焦

有時候，您可能想要共同作業工作階段中的每個人都來查看您在處理的項目。 Live Share 可讓您要求所有人都將其注意力「聚焦」於您，並發出通知讓他們輕鬆回頭追蹤您。

請開啟 VS Code 活動列中的 Live Share 自訂索引標籤或 Live Share [總管] 檢視，然後選取 [聚焦參與者] 圖示。

![聚焦 viewlet 圖示](../media/vscode-focus-viewlet.png)

在您執行命令之後，共同作業工作階段中的每個人就都會收到通知，指出您需要他們注意。

![聚焦快顯通知](../media/vscode-focus-toast.png)

當他們準備好要聚焦在您身上時，便可以直接按一下通知中的 [追蹤]。

## <a name="co-debugging"></a>共同偵錯

Visual Studio Live Share 的共同作業偵錯功能是功能強大且獨特的偵錯問題方式。 除了提供對問題進行偵錯的共同作業體驗之外，它也藉由在主持人的機器上提供共用偵錯工作階段，讓您和工作階段中的其他參與者有能力調查可能是環境特定的問題。

> **安全性提示：** 由於所有參與者都能獨立地瀏覽和編輯檔案，身為主持人的您可能會想要使用 .vsls.json 檔案來限制來賓可存取您專案中的哪些檔案。 您也應該留意到，主控台/REPL 存取表示參與者可以在您的機器上執行命令，因此您只應該與信任的人員進行共同偵錯。 身為來賓，請務必了解到因為這些設定，所以當偵錯工具進入某些受限的檔案時，您可能無法追蹤它。 請參閱[控制檔案存取權和可見性](../reference/security.md#controlling-file-access-and-visibility)以取得詳細資料。

使用它很簡單。

1. 請確定主持人和所有來賓皆已安裝適當的偵錯擴充。 (就技術性層面而言這並非必要，但通常是個不錯的主意。)

2. 身為主持人，如果您尚未針對專案進行設定，請[設定 launch.json](https://code.visualstudio.com/Docs/editor/debugging#_launch-configurations) \(英文\) 以如往常一般地從 VS Code 對應用程式進行偵錯。 您不需要進行任何特殊的設定。

3. 接下來，主持人可以開始如往常一般，使用偵錯索引標籤中的按鈕開始偵錯。

    ![VS Code [偵錯] 按鈕](../media/vscode-debug-button.png)

    > [!TIP]
    > 您也可以從 VS Code 參與 Visual Studio 偵錯工作階段，反之亦然！ 請參閱關於共同偵錯的 [Visual Studio 指示](vs.md#co-debugging)以取得詳細資訊。

偵錯工具附加在主持人端之後，所有來賓會也都會自動附加。 有一個偵錯「工作階段」在主持人的機器上執行的同時，所有參與者都會連線到該偵錯工作階段，且有他們自己的檢視。

![已附加 VS Code 偵錯工具](../media/vscode-debugger.png)

任何人都可以逐步查看偵錯程序，這樣就能在共同作業者之間順暢地切換，而不需要交涉控制權。

> [!NOTE]
> 如需依語言或平台列出偵錯功能的狀態，請參閱[平台支援](../reference/platform-support.md)。

每個共同作業者都可以調查不同變數、跳到呼叫堆疊中的不同檔案、檢查變數，甚至新增或移除中斷點。 共同編輯功能接著會允許每個參與者追蹤其他人的所在位置，以提供在「同時調查問題不同層面」與「共同作業偵錯」之間順暢切換的獨特功能。

> [!NOTE]
> 不過，來賓在唯讀共同作業工作階段中將無法逐步執行偵錯程序。 但他們仍然可以新增或移除中斷點，及檢查變數。

![並行偵錯的動畫](../media/co-debug.gif)

### <a name="change-when-vs-code-joins-debugging-sessions"></a>變更 VS Code 加入偵錯工作階段的時機

根據預設，當主持人共用偵錯工作階段時，來賓會自動附加到該偵錯工作階段。 不過，在某些情況下，您可能覺得此行為會造成干擾。 幸運的是，您可以按照下列步驟來變更它：

請直接**編輯 settings.json** ([檔案] > [喜好設定] > [設定])，新增下列其中一行，然後重新啟動 VS Code：

| 設定 | 行為 |
|---------|----------|
|``"liveshare.joinDebugSessionOption":"Automatic"`` | 預設值。 身為來賓，您會自動加入主持人啟動的任何偵錯工作階段。 |
| ``"liveshare.joinDebugSessionOption":"Prompt"`` | 身為來賓，當主持人啟動共用偵錯工作階段時，您會收到提示詢問您是否要加入。 |
| ``"liveshare.joinDebugSessionOption":"Manual"`` | 身為來賓，您將需要手動加入任何偵錯工作階段。 請參閱[中斷連結與重新附加](#detaching-and-reattaching)。 |

### <a name="detaching-and-reattaching"></a>中斷連結與重新附加

身為來賓，您可能會想要暫時停止偵錯。 幸運的是，您可以直接按一下偵錯工具列中的「停止」圖示來將偵錯工具中斷連結，而不會影響主持人或其他來賓。

![VS Code 偵錯工具 [停止] 按紐](../media/vscode-debug-stop.png)

如果您已更新設定來使自己不會自動附加，或是單純想要稍後再附加，您可以按 **Ctrl+Shift+P / Cmd+Shift+P** 或**按一下**工作階段狀態列項目，並選取 [附加至共用偵錯工作階段]。

![VS Code 附加偵錯工具](../media/vscode-reattach.png)

### <a name="sharing-the-running-application-in-a-browser"></a>在瀏覽器中共用執行中的應用程式

和 Visual Studio 針對如 ASP.NET 等的專案類型不同，Visual Studio Code 並不具有已知「Web 應用程式連接埠」的概念。 不過，如果您是加入來自 Visual Studio 主持人的共同作業工作階段，當偵錯開始時，您可能會看見您的預設瀏覽器自動出現，其接著會自動連線至主持人正在執行的應用程式。 請參閱 [Visual Studio 功能](vs.md#automatic-web-app-sharing)以取得詳細資料。

身為主持人，您可以使用 [共用本機伺服器] 功能，來透過手動共用應用程式或如 RESTful 服務的其他端點以達成類似目的。 Visual Studio 和 VS Code 來賓接著可以在相同的 localhost 連接埠上開啟瀏覽器，以查看正在執行的應用程式。  請參閱[共用伺服器](#share-a-server)以取得詳細資料。

## <a name="share-a-server"></a>共用伺服器

身為共同作業工作階段主持人，您可能偶爾會想要與來賓共用 Web 應用程式或其他在本機執行的伺服器或服務。 這可能是 RESTful 端點、資料庫和其他伺服器。 Visual Studio Live Share 可讓您指定本機連接埠號碼，選擇性地為它命名，然後將它與所有來賓共用。

然後來賓將能夠從其本機機器的相同連接埠存取您在該連接埠上共用的伺服器。 例如，如果您共用的 Web 伺服器**是在連接埠 3000 上執行**，則來賓也能在**自己的機器上**於 http://localhost:3000 存取相同的執行中 Web 伺服器！ 這是透過主持人與來賓之間的 SSH 或 SSL 通道來達成，並且透過服務進行驗證，因此您可確定只有共同作業工作階段中的人員有存取權。

> **安全性提示：** 身為主持人，您應該謹慎選擇所共用的連接埠，並且只使用應用程式連接埠 (而不是共用系統連接埠)。 對於來賓，共用連接埠的行為就如同該伺服器/服務是在他們自己的機器上執行。 這非常有用，但如果共用不適當的連接埠，也可能有風險。

基於安全性考量，其他來賓只能使用在您所指定的連接埠上執行的伺服器。 幸運的是，身為共同作業工作階段的**主持人**，新增連接埠是一件很簡單的事。 方式如下：

1. 請開啟 VS Code 活動列中的 Live Share 自訂索引標籤或 Live Share [總管] 檢視，然後選取 [共用伺服器] 項目或按一下圖示。

    ![VS Code 共用本機伺服器](../media/vscode-share-local-server-viewlet.png)<br />

1. 輸入伺服器所執行的連接埠號碼，並選擇性地提供名稱。

    ![連接埠號碼提示的螢幕擷取畫面](../media/vscode-enter-port.png)<br />

就這麼容易！ 您所指定連接埠上的伺服器，現在會對應到每個來賓 localhost 上的相同連接埠 (除非該連接埠已被占用)！

如果來賓機器上的該連接埠已經使用，系統會自動選取其他連接埠。 幸運的是，身為來賓，您可以在 Live Share [總管] 檢視或 VS Code 活動列的自訂索引標籤中看見目前已共用的連接埠清單 (依名稱排序，若有提供的話)，並查看 [共用伺服器] 清單底下。 選取某個項目將會在您的瀏覽器中開啟該伺服器。 您也能以滑鼠右鍵按一下並選取將伺服器連結複製到剪貼簿的選項。

![VS Code 存取本機伺服器](../media/vscode-access-shared-server-viewlet.png)<br />

請注意，基於安全性考量，「來賓無法」控制在主持人機器上要共用哪個連接埠。

若要以主持人身分**停止**共用本機伺服器，請在 Live Share [總管] 檢視或自訂索引標籤的共用伺服器清單中將游標暫留於該伺服器項目上方，然後按一下 [取消共用伺服器] 圖示。

![VS Code 停止共用伺服器](../media/vscode-stop-sharing-server-viewlet.png)<br />

## <a name="share-a-terminal"></a>共用終端機

新式開發經常會運用各種命令列工具。 幸運的是，Live Share 可讓身為主持人的您選擇與來賓「共用終端機」。 共用的終端機可以是唯讀，或是完全共同作業，讓您和您的來賓都能執行命令並看到結果。 您可以讓來賓看得到終端機輸出，或讓他們操作或執行測試、建置，或甚至將只發生在您機器上的環境特定問題分級。

不過，預設將**不會**共用終端機，因為它們能為來賓至少提供您所執行命令之輸出的唯讀存取權 (或是自行執行命令的能力)。 這樣一來，您可以沒有風險地自由在本機終端機上執行命令，並且只在需要時進行共用。 此外，只有主持人可以啟動共用終端機，這可以防止來賓啟動共用終端機並進行您未預期或您看不到的操作。

身為主持人，您可以開啟 VS Code 活動列中的 [Live Share] 自訂索引標籤或 Live Share [總管] 檢視，然後選取 [共用伺服器] 項目或按一下圖示來共用終端機。

![VS Code 共用終端機](../media/vscode-share-terminal-viewlet.png)<br />

此時，您可以從功能表中選取唯讀或讀取/寫入終端機。 當終端機是讀取/寫入時，包括主持人在內的每個人都可以在終端機中輸入，這樣當來賓在進行您不希望的操作時，您輕鬆就能介入。 不過，為了安全起見，您應該**只在確定來賓確實需要讀取/寫入存取權時才提供此權限**，並在您只想要來賓查看您執行之任何命令的輸出時提供唯讀終端機。

> [!NOTE]
> 如果共同作業工作階段是處於唯讀模式，主持人就只能共用唯讀終端機。

![唯讀或讀取/寫入選取項目](../media/vscode-share-terminal-ro-rw.png)<br />

一旦您選取要啟動的共用終端機類型，VS Code [終端機] 索引標籤底下將會出現新的共用終端機。

![執行中的共用終端機](../media/vscode-share-terminal-up.png)<br />

如果已共用多個終端機，或是您的焦點位於不同的索引標籤中，您可以透過選取共用終端機清單中的項目來將焦點移至特定的終端機。

![共用終端機能轉移焦點](../media/vscode-shared-terminal-focus.png)<br />

若要結束終端機工作階段，請直接輸入 exit、關閉終端機視窗，或按一下 Live Share [總管] 檢視或自訂索引標籤中的 [取消共用終端機]，所有人的連線便會中斷。

## <a name="session-states"></a>工作階段狀態

當您已經啟動或加入共同作業工作階段，並且可存取共用內容之後，Visual Studio Live Share 狀態列項目便會更新其外觀，以反映使用中共同作業工作階段的狀態。

下列是您通常會看到的狀態：

| 狀況 | 狀態列 | 說明 |
|-------|--------------------|-------------|
| 非使用中 | ![VS Code 狀態：非使用中](../media/vscode-status-share.png) | 沒有任何作用中的共同作業工作階段，且未共用任何項目。 |
| 主持人：共用正在進行中 | ![VS Code 狀態：共用正在進行中](../media/vscode-status-sharing.png)| 正在啟動共同作業工作階段，且共用內容很快就會開始。 |
| 主持人：共用 | ![VS Code 狀態：共用作用中 ](../media/vscode-status-active.png)| 共同作業工作階段已啟動，且已共用內容。 |
| 主持人：正在共用唯讀 | ![VS Code 狀態：正在共用唯讀](../media/vscode-status-sharing-read-only.png)| 正在共用唯讀共同作業工作階段。 |
| 來賓：正在加入工作階段 | ![VS Code 狀態：正在加入](../media/vscode-status-joining.png)| 正在加入現有共同作業工作階段。 |
| 來賓：已加入 | ![VS Code 狀態：已加入](../media/vscode-status-active.png) | 已加入且連線至使用中的共同作業工作階段，並接收共用內容。 |
| 來賓：已加入唯讀 | ![VS Code 狀態：已加入唯讀](../media/vscode-status-joined-read-only.png) | 已加入且連線至使用中的唯讀共同作業工作階段。 |

## <a name="guest-limitations"></a>來賓限制

雖然目前來賓在使用上述功能時會遇到一些缺點，但共同作業工作階段主持人會保有所選工具的完整功能。 如需詳細資訊，請參閱下列主題：

- [語言和平台支援](../reference/platform-support.md)
- [延伸模組支援](../reference/extensions.md)
- [所有主要 Bug、功能要求和限制](https://aka.ms/vsls-issues) \(英文\)
- [所有功能要求和限制](https://aka.ms/vsls-feature-requests) \(英文\)
- [疑難排解](../troubleshooting.md)

## <a name="next-steps"></a>後續步驟

請查看下列其他文章以取得詳細資訊。

- [快速入門：共用您的第一個專案](../quickstart/share.md)
- [快速入門：加入您的第一個工作階段](../quickstart/share.md)
- [操作說明：使用 Visual Studio 共同作業](vs.md)
- [Live Share 的連線需求](../reference/connectivity.md)
- [Live Share 的安全性功能](../reference/security.md)
- [Linux 安裝詳細資料](../reference/linux.md)

有問題嗎？ 請參閱[疑難排解](../troubleshooting.md)或[提供意見反應](../support.md)。
