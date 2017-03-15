---
title: "Visual Studio 2017 RC의 오프라인 설치 만들기 | Microsoft 문서"
description: "Visual Studio의 오프라인 설치를 만드는 방법을 알아봅니다."
ms.custom: 
ms.date: 02/14/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-install
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- offline installation [Visual Studio]
- offline install [Visual Studio]
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
ms.sourcegitcommit: d4d1bd45ce697017480b3f63d0c7feb5ab20d2d6
ms.openlocfilehash: 33e765d205aa7ad8a3d8c5b871863ab659092a77
ms.lasthandoff: 02/22/2017

---
# <a name="create-an-offline-installation-of-visual-studio-2017-rc"></a>Visual Studio 2017 RC의 오프라인 설치 만들기

## <a name="create-a-layout"></a>레이아웃 만들기
인터넷에 액세스할 수 없는 다른 컴퓨터에 [Visual Studio 2017 RC](https://www.visualstudio.com/vs/visual-studio-2017-rc/)를 설치하려는 경우 먼저 필요한 Visual Studio 파일 및 구성 요소가 모두 포함된 오프라인 설치 레이아웃을 만들면 됩니다.

그런 다음 만든 오프라인 설치 레이아웃을 사용하여 대상 컴퓨터에 Visual Studio를 설치할 수 있습니다.     

> [!WARNING]
> 현재 Android SDK에는 오프라인 설치 환경을 지원하지 않습니다. 인터넷에 연결되지 않은 컴퓨터에서 Android SDK 설치 항목을 설치하면 설치가 실패할 수 있습니다. 자세한 내용은 이 항목에서 [오프라인 설치 문제 해결](#tshootofflineinstall) 섹션을 참조하세요.


#### <a name="to-create-an-offline-installation-layout-of-visual-studio"></a>Visual Studio의 오프라인 설치 레이아웃을 만들려면
1. 로컬 컴퓨터의 드라이브에 Visual Studio 설치 프로그램 실행 파일을 다운로드합니다.
  예를 들어 [vs_enterprise.exe 파일을 다운로드](https://www.visualstudio.com/vs/visual-studio-2017-rc/)합니다.
2. 명령 프롬프트에서 다음 인수(스위치)를 사용하여 `vs_enterprise.exe`를 실행합니다.

   a. `--layout <path>`를 추가합니다. 여기서 `<path>`는 레이아웃을 다운로드할 위치입니다. 상대 경로(예: `..\vs2017`)는 현재 지원되지 않습니다. 기본적으로 모든 언어가 다운로드됩니다. 예제 A를 참조하세요.

   b. `--lang <language>` 인수를 제공하여 다운로드를 사용 가능한 언어의 하위 집합으로 제한합니다. 여기서 `<language>`는 언어 로캘 중 하나 이상입니다.  예제 B와 예제 C를 참조하세요.

   c. `--add <package ID>` 인수를 제공하여 다운로드를 작업 및 구성 요소의 하위 집합으로 제한합니다. 지정한 작업과 구성 요소(및 해당 종속성)만 다운로드됩니다. 예제 D와 예제 E를 참조하세요.

   Visual Studio 제품별로 정렬된 작업 및 구성 요소 ID의 전체 목록은 [Visual Studio 2017 작업 및 구성 요소 ID](https://aka.ms/vs2017componentids) 페이지를 참조하세요.

### <a name="examples"></a>예제
**예제 A**: 모든 언어의 작업 및 구성 요소를 모두 다운로드합니다.
  > ```vs_enterprise.exe --layout C:\vs2017```

**예제 B**: 한 언어의 작업 및 구성 요소를 모두 다운로드합니다.  
  > ```vs_enterprise.exe --layout C:\vs2017 --lang en-US```

**예제 C**: 여러 언어의 작업 및 구성 요소를 모두 다운로드합니다.
  > ```vs_enterprise.exe --layout C:\vs2017 --lang en-US de-DE ja-JP```

**예제 D**: 모든 언어의 작업 하나를 다운로드합니다.
  > ```vs_enterprise.exe --layout C:\vs2017 --add Microsoft.VisualStudio.Workload.Azure ```

**예제 E**: 세 가지 언어의 작업 두 개와 선택적 구성 요소 하나를 다운로드합니다.
  > ```vs_enterprise.exe --layout C:\vs2017 --add Microsoft.VisualStudio.Workload.Azure Microsoft.VisualStudio.Workload.ManagedDesktop Component.GitHub.VisualStudio --lang en-US de-DE ja-JP ```

  > [!WARNING]
  > setup .exe 파일 이름에 숫자가 포함되면 --layout 매개 변수가 실패합니다. 이 문제를 해결하려면 파일 이름에서 숫자를 제거해야 합니다. &mdash;예를 들어 이름을 *vs_community__198521760.1486960229.exe*에서 ***vs_community.exe***로 바꿉니다.

### <a name="language-locales"></a>언어 로캘

| 언어 로캘 | 언어 |
| -----   | ----- |
| cs-CZ    | 체코어 |
| de-DE    | 독일어 |
| ko-KR    | 영어 |
| es-ES    | 스페인어 |
| fr-FR    | 프랑스어 |
| it-IT    | 이탈리아어 |
| ja-JP    | 일본어 |
| ko-KR    | 한국어 |
| pl-PL    | 폴란드어 |
| pt-BR    | 포르투갈어 - 브라질 |
| ru-RU    | 러시아어 |
| tr-TR    | 터키어 |
| zh-CN    | 중국어 - 간체 |
| zh-TW    | 중국어 - 번체 |


## <a name="install-from-a-layout"></a>레이아웃에서 설치
#### <a name="to-install-visual-studio-from-an-offline-installation-layout"></a>오프라인 설치 레이아웃에서 Visual Studio를 설치하려면
1. 대상 컴퓨터에서 레이아웃 폴더에 있는 **인증서** 폴더로 이동합니다.
2. **인증서** 폴더에서 각 인증서를 마우스 오른쪽 단추로 클릭하고 설치합니다.

  인증서를 설치한 후 암호를 묻는 메시지가 표시되면 **계속**을 클릭합니다.  
3. **레이아웃** 폴더에서 `vs_enterprise.exe`를 실행합니다.

참고: 부분 레이아웃에서 설치하고 레이아웃에서 사용할 수 없는 작업, 구성 요소 또는 언어를 선택하는 경우 설치 프로그램이 다운로드를 시도합니다.  인터넷에 액세스할 수 없는 경우 해당 항목을 설치하지 못합니다.

> [!CAUTION]
> 오프라인 설치 레이아웃은 현재 일부 파일을 모든 사용자의 액세스를 차단하는 제한된 사용 권한(ACL)으로 만듭니다.  오프라인 설치를 공유하기 *전에* 다른 사용자에게 읽기 권한을 부여하도록 사용 권한(ACL)을 조정해야 합니다.

## <a name="update-an-installation-layout"></a>설치 레이아웃 업데이트
Visual Studio 2017 RC용 업데이트가 제공되면 `--layout` 명령을 다시 실행하고 동일한 레이아웃 폴더를 가리켜 최신 구성 요소가 폴더에 포함되도록 합니다. 마지막으로 `--layout`을 실행한 후 업데이트된 구성 요소만 다운로드됩니다.

## <a id="tshootofflineinstall"> </a>설치 레이아웃 문제 해결
오프라인 설치 캐시에서 오프라인으로 설치하는 경우 일부 구성 요소와 패키지를 설치할 수 없다는 경고 메시지가 표시될 수도 있습니다. 다음 표에는 이러한 시나리오에 대한 가능한 해결 방법이 포함되어 있습니다.

| 구성 요소 또는 패키지 | 솔루션 |
| -------------------- | -------- |
|Android SDK 설치(API 수준)| Android SDK(API 수준) 패키지를 설치하려면 인터넷 연결이 있어야 합니다. 제한된 네트워크에 있는 경우 Visual Studio를 설치할 때 다음 URL에 대한 액세스를 허용해야 합니다. <br><br> - http://dl.google.com:443 <br>- http://dl-ssl.google.com:443 <br>  - https://dl-ssl.google.com/android/repository/*<br><br>가능한 프록시 설정 문제를 해결하는 방법에 대한 자세한 내용은 [Visual Studio install failures (Android SDK Setup) behind a Proxy](https://blogs.msdn.microsoft.com/peterhauge/2016/09/22/visual-studio-2015-install-failures-android-sdk-setup-behind-a-proxy/)(프록시를 사용하는 경우의 Visual Studio 설치 오류(Android SDK 설치)) 블로그 게시물을 참조하세요.  |  

 > [!IMPORTANT]
 > Visual Studio 2017 RC는 일반적으로 프로덕션 환경에서 사용할 수 있지만 설치 UI에서 "미리 보기"로 표시된 워크로드 및 구성 요소는 프로덕션 환경에서 사용할 수 없습니다.

 ## <a name="see-also"></a>참고 항목
 * [Visual Studio 설치](install-visual-studio.md)
 * [명령줄 매개 변수를 사용하여 Visual Studio 설치](use-command-line-parameters-to-install-visual-studio.md)
 * [Visual Studio의 문제 보고](../ide/how-to-report-a-problem-with-visual-studio-2017.md)

