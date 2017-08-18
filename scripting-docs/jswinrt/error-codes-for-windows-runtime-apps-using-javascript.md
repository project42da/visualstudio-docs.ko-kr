---
title: "JavaScript를 사용하는 Windows 런타임 앱에 대한 오류 코드 | Microsoft Docs"
ms.custom: 
ms.date: 05/10/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- javascript
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- JavaScript, Windows Runtime error codes
- VS.WebClient.Help.APPHOST9601
- VS.WebClient.Help.APPHOST9602
- VS.WebClient.Help.APPHOST9603
- VS.WebClient.Help.APPHOST9604
- VS.WebClient.Help.APPHOST9605
- VS.WebClient.Help.APPHOST9606
- VS.WebClient.Help.APPHOST9607
- VS.WebClient.Help.APPHOST9608
- VS.WebClient.Help.APPHOST9610
- VS.WebClient.Help.APPHOST9611
- VS.WebClient.Help.APPHOST9613
- VS.WebClient.Help.APPHOST9614
- VS.WebClient.Help.APPHOST9615
- VS.WebClient.Help.APPHOST9616
- VS.WebClient.Help.APPHOST9617
- VS.WebClient.Help.APPHOST9618
- VS.WebClient.Help.APPHOST9619
- VS.WebClient.Help.APPHOST9620
- VS.WebClient.Help.APPHOST9623
- VS.WebClient.Help.APPHOST9624
- VS.WebClient.Help.APPHOST9626
ms.assetid: 4c6d4e90-602a-4b56-ae74-3458929da442
caps.latest.revision: 1
author: erikadoyle
ms.author: edoyle
manager: jken
ms.translationtype: HT
ms.sourcegitcommit: 47057e9611b824c17077b9127f8d2f8b192d6eb8
ms.openlocfilehash: 89b91a3246d0a6e2980459c2c35c7361168bccd4
ms.contentlocale: ko-kr
ms.lasthandoff: 08/11/2017

---
# <a name="error-codes-for-windows-runtime-apps-using-javascript"></a>JavaScript를 사용하는 Windows 런타임 앱에 대한 오류 코드
다음은 JavaScript를 사용하여 Windows 런타임 앱을 개발할 때 Microsoft Visual Studio 콘솔에 표시되는 오류 코드입니다.
  
오류 | 설명
----- | -------
APPHOST9601: “*remoteURI*를 로드할 수 없습니다. 앱이 로컬 컨텍스트에서 원격 웹 콘텐츠를 로드할 수 없습니다.” | 웹 컨텍스트에서 허용되는 사항에 대한 자세한 내용은 [컨텍스트별 기능 및 제한 사항](https://msdn.microsoft.com/en-us/library/windows/apps/xaml/hh465373.aspx)을 참조하세요.
APPHOST9602: “’javascript:’는 유효하지 않은 특성 값이므로 무시됩니다. 로컬 컨텍스트에서 ‘javascript:’ URI를 사용하지 마세요.” | 보안상의 이유로 로컬 컨텍스트에서 ‘javascript:’ URI를 사용할 수 없습니다. 로컬 컨텍스트에서 허용되는 사항에 대한 자세한 내용은 [컨텍스트별 기능 및 제한 사항](https://msdn.microsoft.com/en-us/library/windows/apps/xaml/hh465373.aspx)을 참조하세요.
APPHOST9603: “클래스 ID *classID*가 있는 ActiveX 플러그 인을 로드할 수 없습니다.  앱에서 ActiveX 제어를 로드할 수 없습니다.” | JavaScript를 사용하는 Windows 런타임 앱에서는 사용자 지정 Microsoft ActiveXcontrols를 지원하지 않습니다. UI 컨트롤이 필요하면 표준 웹 컨트롤인 제어 라이브러리를 사용하거나 고유 사용자 지정 컨트롤을 만듭니다. 사용자 지정 논리를 수행해야 하는 경우 사용자 지정 Windows 런타임 개체를 대신 만듭니다. 기타 HTML, CSS 및 JavaScript 차이점에 대한 정보는 [HTML, CSS 및 JavaScript 기능과 차이점](https://msdn.microsoft.com/en-us/library/windows/apps/xaml/hh465380.aspx)을 참조하세요.
APPHOST9604: “유효한 문자 인코딩을 사용하므로 *uri*로 이동할 수 없습니다.  앱에서 UTF8으로 인코딩된 파일로만 이동할 수 있습니다.” | Windows 런타임에서 액세스하는 모든 HTML, JavaScript 및 CSS는 UTF-8(8비트 유니코드 변환 형식)으로 인코딩해야 합니다. 기타 HTML, CSS 및 JavaScript 차이점에 대한 정보는 [HTML, CSS 및 JavaScript 기능과 차이점](https://msdn.microsoft.com/en-us/library/windows/apps/xaml/hh465380.aspx)을 참조하세요.
APPHOST9605: “대상 URI가 더 높은 보안 영역에 있으므로 *sourceURI*에서 *targetURI*로 이동할 수 없습니다. 웹 컨텍스트 URI에서 로컬 컨텍스트 URI로 이동하고, MSApp.addPublicLocalApplicationUri 메서드를 사용하여 로컬 컨텍스트 URI를 등록한 경우가 아니면 보안이 낮은 영역에서 보안이 높은 영역으로 이동할 수 없습니다.” | 자세한 내용은 [MSApp.addPublicLocalApplicationUri](https://msdn.microsoft.com/en-us/library/windows/apps/xaml/hh465759.aspx)를 참조하세요.
APPHOST9606: “HTTP 연결을 사용하고 ms-https-connections-only 메타 요소가 있으므로 *uri*를 로드할 수 없습니다. ms-https-connections-only 메타 요소를 사용하는 경우 HTTPS 연결만 허용됩니다. HTTPS 연결을 사용합니다. 보안 연결이 필요 없으면 메타 요소를 제거합니다.” | 자세한 내용은 [HTTPS 연결을 요구하는 방법](https://msdn.microsoft.com/en-us/library/windows/apps/xaml/hh452771.aspx)을 참조하세요.
APPHOST9607: “*failureCode* 오류로 인해 앱에서 *uri*의 URI를 시작할 수 없습니다.” | 이 오류는 일반적으로 누락된 리소스 또는 유효하지 않은 파일로 인해 발생합니다.
APPHOST9608: “*errorCode* 오류로 인해 앱에서 about:blank 페이지로 이동할 수 없습니다.” | 
APPHOST9610: “사용자 지정 오류 페이지로 이동하려고 준비하는 동안 앱에서 *errorCode* 오류를 발견했습니다.” |
APPHOST9611: “*errorCode* 오류로 인해 앱에서 사용자 지정 오류 페이지로 이동할 수 없습니다.” |
APPHOST9613: “*errorCode* 오류로 인해 앱에서 * uri*로 이동할 수 없습니다.” | 
APPHOST9614: “iframe의 문서에서 *requestedDocMode* 문서 모드를 요청했지만 시스템에서 *currentDocMode* 문서 모드를 적용합니다. iframe에서 *currentDocMode* 문서 모드를 사용합니다.” | 원격 웹 콘텐츠를 표시하는 데 대한 자세한 내용은 [외부 웹 페이지에 연결하는 방법](https://msdn.microsoft.com/en-us/library/windows/apps/xaml/hh780594.aspx)을 참조하세요.
APPHOST9615: “로컬 컨텍스트 외부에서 프로그래밍 방식으로 호출되었으므로 앱에서 *uri*에 있는 파일을 다운로드할 수 없습니다.” | 웹 컨텍스트의 콘텐츠에서 프로그래밍 방식으로 파일을 다운로드하려고 하면 발생합니다.
APPHOST9616: “이 URI에서 지리적 위치 API를 사용할 수 없습니다.  지리적 위치 API는 패키지의 일부이거나 매니페스트의 ApplicationContentUris 요소에 포함된 URI에서만 호출할 수 있습니다.” | 웹 컨텍스트에서 허용되는 사항에 대한 자세한 내용은 [컨텍스트별 기능 및 제한 사항](https://msdn.microsoft.com/en-us/library/windows/apps/xaml/hh465373.aspx)을 참조하세요.
APPHOST9617: “이 URI에서 클립보드 API를 사용할 수 없습니다.  클립보드 API 패키지의 일부이거나 매니페스트의 ApplicationContentUris 요소에 포함된 URI에서만 호출할 수 있습니다.” | 웹 컨텍스트에서 허용되는 사항에 대한 자세한 내용은 [컨텍스트별 기능 및 제한 사항](https://msdn.microsoft.com/en-us/library/windows/apps/xaml/hh465373.aspx)을 참조하세요.
APPHOST9618: “이 URI에서는 window.close를 사용할 수 없습니다.  window.close 메서드는 ms-appx URI 스키마로 로드된 패키징된 콘텐츠에서만 호출할 수 있습니다.” | 웹 컨텍스트에서 허용되는 사항에 대한 자세한 내용은 [컨텍스트별 기능 및 제한 사항](https://msdn.microsoft.com/en-us/library/windows/apps/xaml/hh465373.aspx)을 참조하세요.
APPHOST9619: “웹 컨텍스트의 페이지는 앱의 최상위 문서일 수 없으므로 앱에서 *uri*로 이동할 수 없습니다. 대신 iframe에서 페이지를 로드합니다.” | 최상위 페이지에서 원격 웹 페이지로 이동할 수 없지만 앱에서 [iframe](https://msdn.microsoft.com/en-us/library/ms535258(v=vs.85).aspx)에 웹 페이지를 표시할 수 있습니다. 원격 웹 콘텐츠를 표시하는 데 대한 자세한 내용은 [외부 웹 페이지에 연결하는 방법](https://msdn.microsoft.com/en-us/library/windows/apps/xaml/hh780594.aspx)을 참조하세요.
APPHOST9620: “HTTP 연결을 사용하고 ms-https-connections-only 메타 요소가 있으므로 이 앱이 종료되었습니다. ms-https-connections-only 메타 요소를 사용하는 경우 HTTPS 연결만 허용됩니다. HTTPS 연결을 사용합니다. 보안 연결이 필요 없으면 메타 요소를 제거합니다.” | 자세한 내용은 [HTTPS 연결을 요구하는 방법](https://msdn.microsoft.com/en-us/library/windows/apps/xaml/hh452771.aspx)을 참조하세요.
APPHOST9623: “*errorCode* 오류로 인해 앱에서 *url*을 확인할 수 없습니다.” | 이 오류는 일반적으로 누락된 파일로 인해 발생합니다.  
APPHOST9624: “URL에서 다른 앱을 시작하므로, 앱에서 스크립트를 사용하여 *url* URL을 로드할 수 없습니다. 직접 사용자가 개입해야만 다른 앱을 시작할 수 있습니다.” | 앱에서 다른 앱을 직접 시작할 수 없습니다. 앱에서 특정 계약을 구현할 때 사용자가 다른 앱을 시작할 수 있습니다. 자세한 내용은 [앱 계약 및 확장](https://msdn.microsoft.com/en-us/library/windows/apps/xaml/hh464906.aspx)을 참조하세요.
APPHOST9626: “리소스 파일 `ms-appx://1d33240b-0b00-40e4-a416-a4750c48787f/ja-jp\images\logo.scale-140.png`에 대한 직접 참조가 검색되었습니다. 디버깅 환경 외부에서 사용할 때 이 참조 때문에 실패하게 됩니다.” | `logo.scale-140.png`의 파일 경로로 인해 이 PNG 파일이 로컬화된 리소스로 취급되므로, 로컬화된 리소스를 직접 참조할 수 없다는 오류가 발생합니다. 이 파일을 언어 리소스로 사용하려는 경우 [앱 세계화(HTML)](https://msdn.microsoft.com/en-us/library/windows/apps/xaml/hh465006.aspx)를 참조하세요. 그렇지 않으면 문제가 있는 디렉터리의 이름을 바꿔봅니다.
  
## <a name="see-also"></a>참고 항목  
 [JavaScript에서 Windows 런타임 사용](../jswinrt/using-the-windows-runtime-in-javascript.md)
