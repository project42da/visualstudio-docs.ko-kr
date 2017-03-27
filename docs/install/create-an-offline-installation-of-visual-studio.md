---
title: "Visual Studio 2017용 오프라인 설치 관리자 만들기 | Microsoft Docs"
description: "Visual Studio용 오프라인 설치 관리자를 만드는 방법에 대해 알아봅니다."
ms.custom: 
ms.date: 03/07/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-install
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- offline installation [Visual Studio]
- offline install [Visual Studio]
- offline installer [Visual Studio]
- ISO [Visual Studio]
ms.assetid: 7bd7e724-7bfd-43f1-9935-981919be5a00
author: TerryGLee
ms.author: tglee
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: 91fde66abf2f325ef0a6a0a2fd30e36981f44033
ms.openlocfilehash: acb47946c29d99cb53b34d67fe8a26f5611307f9
ms.lasthandoff: 03/08/2017

---
# <a name="create-an-offline-installer-for-visual-studio-2017"></a>Visual Studio 2017용 오프라인 설치 관리자 만들기
많은 고객이 [Visual Studio 2017](https://go.microsoft.com/fwlink/?linkid=844067)용 오프라인 설치 관리자를 원한다는 것을 알고 있습니다. ISO 이미지를 제공하지는 않지만 오프라인일 때 설치하는 데 사용할 수 있는 폴더를 만드는 것은 쉽습니다.

방법은 다음과 같습니다.

## <a name="download-the-setup-file-you-want"></a>원하는 설치 파일 다운로드
원하는 Visual Studio 버전을 **[다운로드](https://www.visualstudio.com/downloads?utm_source=mscom&utm_campaign=msdocs)**합니다. **저장**을 클릭한 다음 **폴더 열기**를 클릭합니다.

설치 파일&mdash;또는 더 구체적으로 부트스트래퍼 파일&mdash;다음 중 하나와 일치합니다.

|버전 | 파일|  
|-------------|-----------------------|  
|Visual Studio Enterprise |**vs_enterprise.exe**|  
|Visual Studio Professional |**vs_professional.exe**|  
|Visual Studio 커뮤니티 |**vs_community.exe**|

## <a name="create-an-offline-installation-folder"></a>오프라인 설치 관리자 폴더 만들기
모든 언어와 기능을 포함한 오프라인 설치를 만들려면 다음 예제의 명령 중 하나를 사용합니다.

다운로드 디렉터리에서 명령을 실행해야 합니다. 일반적으로 Windows 10을 실행하는 컴퓨터의 경우 `C:\Users\<username>\Downloads`입니다.

- Visual Studio Enterprise의 경우 다음을 실행합니다. <br>  ```vs_enterprise.exe --layout c:\vs2017offline```
- Visual Studio Professional의 경우 다음을 실행합니다. <br> ```vs_professional.exe --layout c:\vs2017offline```
- Visual Studio Community의 경우 다음을 실행합니다. <br> ```vs_community.exe --layout c:\vs2017offline```

더 많은 예제를 보려면 이 페이지의 [오프라인 설치 관리자를 사용자 지정하는 방법](#how-to-customize-your-offline- installer) 섹션을 참조하세요.

## <a name="install-from-the-offline-installation-folder"></a>오프라인 설치 폴더에서 설치
지금 또는 나중에 오프라인 설치를 실행합니다. 사용자가 선택하는 것이지만, 그러한 경우 다음 단계를 따르세요.

  1. 인증서를 설치합니다(인증서는 Layout 폴더 내의 Certificates 폴더에 있습니다. 각각을 마우스 오른쪽 단추로 클릭만 하면 설치됩니다.)

  2. 설치 파일을 실행합니다. 예를 들어 다음을 실행합니다. <br> ```c:\vs2017offline\vs_enterprise.exe```

## <a name="additional-tips-for-offline-installers"></a>오프라인 설치 관리자에 대한 추가 팁
오프라인 설치 관리자는 쉽게 사용자 지정하거나 업데이트할 수 있으며, 여기서 그 방법에 대해 알아보겠습니다. 오프라인 설치 관리자에 문제가 발생하면 문제 해결 및 지원 정보도 제공됩니다.

### <a name="how-to-customize-your-offline-installer"></a>오프라인 설치 관리자를 사용자 지정하는 방법
오프라인 설치 관리자를 사용자 지정하는 데 사용할 수 있는 다양한 옵션이 있습니다. 다음은 [언어 로캘](use-command-line-parameters-to-install-visual-studio.md#list-of-language-locales)로 사용자 지정하는 방법의 몇 가지 예제입니다.

 - 한 언어의 작업과 구성 요소를 모두 다운로드하려면 다음을 실행합니다. <br>```vs_enterprise.exe --layout C:\vs2017offline --lang en-US```
 - 여러 언어의 작업과 구성 요소를 모두 다운로드하려면 다음을 실행합니다. <br>```vs_enterprise.exe --layout C:\vs2017offline --lang en-US de-DE ja-JP```
 - 모든 언어의 작업 하나만 다운로드하려면 다음을 실행합니다. <br> ```vs_enterprise.exe --layout C:\vs2017offline --add Microsoft.VisualStudio.Workload.Azure ```
 - 세 가지 언어의 작업 두 개와 선택적 구성 요소 하나를 다운로드하려면 다음을 실행합니다. <br>```vs_enterprise.exe --layout C:\vs2017offline --add Microsoft.VisualStudio.Workload.Azure Microsoft.VisualStudio.Workload.ManagedDesktop Component.GitHub.VisualStudio --lang en-US de-DE ja-JP ``` 설치를 사용자 지정하는 데 사용할 수 있는 옵션에 대한 자세한 내용은 [명령줄 매개 변수를 사용하여 Visual Studio 2017 설치](use-command-line-parameters-to-install-visual-studio.md) 페이지를 참조하세요.


### <a name="how-to-update-an-offline-installer"></a>오프라인 설치 관리자를 업데이트하는 방법
나중에 오프라인 설치 관리자를 업데이트할 수 있습니다. 방법은 다음과 같습니다.
* 오프라인 설치 폴더에서 설치한 Visual Studio 인스턴스를 업데이트하려면 Visual Studio 설치 관리자를 실행한 다음 **업데이트**를 클릭합니다.
* 최신 업데이트가 포함되도록 오프라인 설치 폴더를 새로 고치려면 ```--layout``` 명령을 다시 실행합니다. 이전에 사용한 것과 동일한 폴더를 가리키도록 합니다. 이렇게 하면 ```--layout```을 마지막으로 실행한 이후에 업데이트된 구성 요소만 다운로드합니다.


오프라인 설치를 업데이트하려면 `--layout` 명령을 다시 실행합니다. 이전에 사용한 것과 동일한 폴더를 가리키도록 합니다. 이렇게 하면 `--layout`을 마지막으로 실행한 이후에 업데이트된 구성 요소만 다운로드합니다.

### <a name="how-to-troubleshoot-an-offline-installer"></a>오프라인 설치 관리자 문제를 해결하는 방법
때로는 무엇인가 잘못됩니다. 다음 표에서는 알려진 문제 및 도움이 되는 몇 가지 해결 방법을 보여 줍니다.

| 문제       | 항목                   | 솔루션 |
| ----------- | ---------------------- | -------- |
| 일부 구성 요소 및 패키지를 설치할 수 없다는 경고 메시지가 나타납니다.  | Android SDK 설치(API 수준) | Android SDK(API 수준) 패키지를 포함하려면 오프라인 설치 관리자를 만들 때 인터넷에 연결되어 있어야 합니다. 제한된 네트워크에 있는 경우 다음 URL에 대한 액세스를 허용해야 합니다. <br><br> - http://dl.google.com:443 <br> - http://dl-ssl.google.com:443 <br>  - https://dl-ssl.google.com/android/repository/*<br><br>가능한 프록시 설정 문제를 해결하는 방법에 대한 자세한 내용은 [Visual Studio install failures (Android SDK Setup) behind a Proxy](https://blogs.msdn.microsoft.com/peterhauge/2016/09/22/visual-studio-2015-install-failures-android-sdk-setup-behind-a-proxy/)(프록시를 사용하는 경우의 Visual Studio 설치 오류(Android SDK 설치)) 블로그 게시물을 참조하세요.  |  
| 사용자에게 파일에 액세스할 수 있는 권한이 없습니다. | 권한(ACL) | 오프라인 설치를 공유하기 *전에* 먼저 다른 사용자에게 읽기 액세스 권한을 부여하도록 권한(ACL)을 조정해야 합니다. |
| 새 작업, 구성 요소 또는 언어가 설치되지 않습니다.  | `--layout`  | 부분 레이아웃에서 설치하고 이전 레이아웃에서 사용할 수 없는 작업, 구성 요소 또는 언어를 선택하는 경우 인터넷에 액세스할 수 있는지 확인합니다. |

### <a name="how-to-get-support-for-your-offline-installer"></a>오프라인 설치 관리자에 대한 지원을 받는 방법
오프라인 설치에 문제가 발생하는 경우와 관련하여 자세히 알려고 합니다. [문제 보고](../ide/how-to-report-a-problem-with-visual-studio-2017.md)를 사용하여 알리는 것이 가장 좋습니다. 이 도구를 사용하면 문제를 진단하고 해결하는 데 필요한 원격 분석과 로그를 보낼 수 있습니다.

사용 가능한 다른 지원 옵션도 있습니다. 관련 목록에 대해서는 [Talk to us](../ide/how-to-report-a-problem-with-visual-studio-2017.md)(문의하기) 페이지를 참조하세요.


## <a name="see-also"></a>참고 항목
* [Visual Studio 설치](install-visual-studio.md)
* [Visual Studio 관리자 가이드](visual-studio-administrator-guide.md)
* [명령줄 매개 변수를 사용하여 Visual Studio 설치](use-command-line-parameters-to-install-visual-studio.md)
* [Visual Studio 작업 및 구성 요소 ID](workload-and-component-ids.md)

