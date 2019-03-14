---
title: 常見問題集-Visual Studio 即時共用 |Microsoft Docs
description: 有關 Visual Studio Live Share 常見問題的問題。
ms.custom: ''
ms.date: 05/05/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- liveshare
ms.topic: reference
author: lostintangent
ms.author: joncart
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 7e9151d513127fa46c3936b359afd0127e4a5fca
ms.sourcegitcommit: 4f733c9053848f26da03d47050bcb734f6c98b31
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2019
ms.locfileid: "57255573"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="frequently-asked-questions"></a>常見問題集

## <a name="what-is-live-share"></a>什麼是 Live Share？
即時共用可讓開發人員共用程式碼基底和其內容，讓您直接從您現有的工具 （Visual Studio 2017 或 Visual Studio Code） 取得即時、 雙向、 共同作業。 Live Share，與您小組成員可以讀取、 瀏覽、 編輯和偵錯您與其共用它們，順利、 安全的專案。

## <a name="what-are-the-tooling-requirements-for-using-live-share"></a>使用 Live Share 工具需求有哪些？
[核心功能](#what-are-the-core-capabilities-of-live-share)Live Share 的完全支援下列工具：

* [Visual Studio 2017 (15.6+)](https://visualstudio.microsoft.com/vs/)
* [Visual Studio Code](https://code.visualstudio.com/)

在預覽期間，Live Share 會快速反覆運算來回應使用者意見反應，可能需要我們充分利用 Visual Studio 內的功能，Visual Studio Code，才可在其各自的預覽/insider 版本中。 我們會指出哪些功能需要較新版本的 VS 或 VS Code 文件中。 比方說，本機復原/取消復原支援需要 Visual Studio 2017 15.7 +。

## <a name="what-are-the-core-capabilities-of-live-share"></a>Live Share 的核心功能有哪些？
Live Share 可讓您分享您程式碼基底與您的小組成員透過安全連線。 使用 Live Share，您就能夠以共同作業方式編輯工作區中的多個檔案，並更重要的是偵錯您的應用程式，與小組成員。 共同編輯您的編輯期間會立即看見您的小組成員。 共同偵錯期間就會共用相同的偵錯工作階段中，您的應用程式。 這表示您和小組成員可以控制以中斷點和步驟，在程式執行，但您可以單獨檢查變數、 監看式、 區域變數及 Repl （例如 Visual Studio 中的即時運算視窗）。

即時共用具有各種不同的使用案例，例如： 在一起，調查 bug 顯示不會在另一個人的電腦上重現的問題解決設計問題，配對程式設計、 進行撰寫程式碼面試、 顧問團隊的其他成員或執行特定程式碼檢閱。

## <a name="by-using-live-share-is-my-code-stored-on-a-microsoft-server"></a>藉由使用 Live Share，是我的 Microsoft 伺服器上儲存的程式碼？
否，共用程式碼位於單獨的開發人員起始共用的機器。 它不會存放或上傳至雲端以任何方式。 相反地，Live Share 只安全之間建立連接，您和小組成員 （也就是加密的端對端），並不會檢查或收集任何資料，在共用的程式碼。

## <a name="does-this-remote-based-model-work-anywhere-is-it-peer-to-peer"></a>這個遠端基礎的模型是否使用任何地方？ 它是對等項目-嗎？
即時共用的唯一要求就是共用的人員和其小組每個能夠存取網際網路。 Azure 轉送可促進共同作業工作階段期間的小組成員之間的通訊安全。 您的工作區 （也就是原始程式檔） 不會儲存在雲端中。 沒有特殊的對等連線是必要的不過其中一個可能會用來減少延遲。 請參閱[變更連線模式](https://aka.ms/vsls-docs/connection-mode)在我們的文件，如需詳細資訊。

## <a name="what-is-shared-during-a-live-share-session"></a>什麼是 Live Share 工作階段期間共用？
即時的共用不會傳輸所有的鍵盤和滑鼠輸入。 它只會針對每個小組成員的機器的共同作業活動所需的資料進行通訊。 例如，當您共用您的工作區時，會共用您的資料夾結構。 當您以共同作業方式編輯檔案時，會共用檔案的內容。 當您以共同作業方式偵錯 （例如逐步執行） 的偵錯動作和狀態 （例如呼叫堆疊和區域變數） 會共用。

## <a name="when-will-live-share-be-released"></a>Live Share 將何時發行？
即時的共用是現已推出公開預覽 ！ 我們想要密切合作，開發人員測試的預覽位元，以收集意見反應，並確保我們可以提供最佳體驗，更廣泛地開啟服務之前。

## <a name="how-much-will-it-cost"></a>將它費用是多少？
我們致力於實質性免費層次的 Visual Studio Live Share 供開發人員持續使用。 我們將會評估付費層次，利用進階功能的引進當我們深入了解社群的需求。

## <a name="how-is-my-code-shared-with-other-teammates"></a>與其他小組成員如何共用我的程式碼？
使用 Live Share，當您進行，小組成員可以存取它透過安全的雲端服務該遠端命令從您的編輯器，正在處理可用的程式碼。 小組成員可以開啟和編輯的檔案，而不需要將它們儲存在雲端或永久地將它們儲存在您小組成員的電腦上。

即時共用可讓您立即存取專案樹狀結構、 程式碼巡覽和搜尋等功能。 它也可讓您的小組成員，才會受益於編輯器增強功能，例如 IntelliSense。

## <a name="what-happens-if-a-user-goes-offline-or-stops-sharing"></a>如果使用者將會離線，或停止共用發生什麼事？
遠端的模型會需要透過 Live Share 和其小組分享開發人員必須連線才能連接。 如果您小組成員嘗試使用 Live Share，當您離線時，他們將無法加入此工作階段，直到您一次在線上。 此外，一旦共同作業停駐點 （例如您關閉編輯器、 離線，或停止共用），然後進一步動作或小組成員所存取的檔案會立即停用。

## <a name="what-about-screen-sharing"></a>那麼螢幕共用呢？
Live Share 可讓您共用您的專案程式碼和其內容。 這表示您的小組可以輕鬆地一頭栽進程式碼基底，並使用您使用其熟悉的工具。 您的編輯器或其他應用程式不共用或可檢視依您的小組成員，而且您不需要變更工作型態，或使用網頁型應用程式。

即時的共用不會取代您可能想要顯示的功能表項目或討論視覺效果，您的應用程式或您編輯器的螢幕共用。 相反地，您可以選擇使用 Live Share 以及對談、 語音、 視訊和螢幕共用。

## <a name="what-about-other-collaboration-tools"></a>其他共同作業工具呢？
即時共用可以搭配對談、 立即訊息或電子郵件技術。 我們觀察到許多開發人員之間的合作互動開始在這些工具。 不過，當討論與程式碼有關，而且常會收到很直接的點太多個內容需要難說明文字、 程式碼片段或單一檔案-有問題。

即時共用可用於許多項目，例如： 搜尋說明問題，解決 bug，配對程式設計、 進行編碼的訪談中，或執行臨機操作之前，請檢視程式碼認可或提取要求。

## <a name="what-about-other-web-editors"></a>其他 web 編輯器呢？
以 web 為基礎的編輯器，這兩個小組成員必須使用相同的 web 應用程式取得共同作業的優點，可能不到其主要、 日常的編輯器。 許多 web 架構的編輯器會假設您是建置和部署到通常裝載在雲端環境中的虛擬機器。

雖然這可能是適合許多情況下，開發人員通常會想要在不裝載在 VM 中部署或雲端中的應用程式上共同作業。  Live Share，您和您的小組可以使用此工具的生態系統，除了在網頁的編輯器中提供的相同功能的功能。

即時共用更進一步的步驟，並可讓您共用的偵錯工作階段。  這可讓您特別適用於登錄其他人來協助您找出您的電腦而不改變他們的開發工作流程，或需要改變應用程式的設計只會發生的問題。

## <a name="which-languages-and-platforms-will-be-supported-in-the-preview"></a>將在預覽中支援哪些語言及平台？
不過，我們的目標是以支援各種不同的橫向顯示的語言及平台，以確保我們可以啟用豐富的共同作業，無論正在開發的應用程式類型。 請參閱[語言和支援的平台](reference/platform-support.md)如需有關哪些今天的文章。 我們想要改善此圖片移動向前根據意見反應，這是個開端。

## <a name="how-many-developers-can-join-a-collaboration-session"></a>多少開發人員可以加入共同作業工作階段？
我們目前支援五個並行的來賓，除了開發人員 （「 主機 」） 共用其專案。 因此，共同作業工作階段可以總共有六個的開發人員在它在任何指定時間。 話雖如此，這是一個區域我們要尋找的意見反應，因此，如果您有一個使用案例需要更高的限制，請[讓我們知道](https://github.com/MicrosoftDocs/live-share/issues/229)！

## <a name="what-is-the-roadmap"></a>藍圖是什麼？
您可以檢視一組已知的問題和藍圖項目[此處](https://aka.ms/vsls-issues)。 如果您想要請參閱僅功能要求，而不是所有的問題，請參閱[此處](https://aka.ms/vsls-feature-requests)。 我們鼓勵您附議現有的項目，提出新功能要求，並記錄錯誤報告，以協助我們圖形的方向，邁向未來的產品。

## <a name="see-also"></a>另請參閱

- [語言和平台支援](platform-support.md)
- [Live Share 的連線需求](reference/connectivity.md)
- [Live Share 的安全性功能](reference/security.md)
- [所有主要 bug、 功能要求和限制](https://aka.ms/vsls-issues)
- [所有的功能要求和限制](https://aka.ms/vsls-feature-requests)

有問題嗎？ 請參閱[疑難排解](troubleshooting.md)或[提供意見反應](support.md)。
