---
title: "Mac용 Visual Studio 설치"
description: "Mac용 Visual Studio 및 플랫폼 간 개발에 필요한 추가 구성 요소를 설치하는 방법에 대한 지침입니다."
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.topic: article
ms.technology: vs-ide-install
ms.assetid: 22B1F2CD-32AE-464D-80AC-C8AB4786B015
ms.translationtype: HT
ms.sourcegitcommit: e2b7ff9126e1cc38ac2e58d6be339b656a024e7f
ms.openlocfilehash: 24d2fa5f9054e621cd5167692a2571e9275c2bae
ms.contentlocale: ko-kr
ms.lasthandoff: 08/11/2017

---

# <a name="setup-and-install-visual-studio-for-mac"></a>Mac용 Visual Studio 설정 및 설치

## <a name="setup"></a>설정

네이티브 플랫폼 간 앱 개발을 시작하려면 Mac용 Visual Studio를 다운로드할 때 설치 및 설정해야 하는 몇 가지 사항이 있습니다.

Visual Studio에서 iOS를 사용하는 경우 다음 사항이 필요합니다.

* macOS Sierra 10.12 이상이 설치된 Mac
* Xcode 8.3
* Apple ID. Apple ID가 없으면 https://appleid.apple.com에서 새로 만들 수 있습니다. Xcode를 설치하고 서명하려면 Apple ID가 있어야 합니다.

## <a name="install"></a>설치

1. [https://www.visualstudio.com/](https://www.visualstudio.com/)에서 Mac용 Visual Studio를 다운로드합니다.

2. 설치 관리자 패키지가 다운로드되면 **VisualStudioInstaller.dmg** 파일을 클릭하여 설치 관리자를 탑재하고 다음 이미지와 같이 로고를 두 번 클릭하여 실행합니다.

  ![설치 관리자 대화 상자](media/installer-image1.png)

3. 다음 이미지와 비슷한 경고 대화 상자가 표시될 수도 있습니다. 이 경우 **열기**를 클릭합니다.

  ![경고 대화 상자](media/installer-image2.png)

4. 설치 관리자가 시스템을 검사하여 설치 또는 업데이트해야 하는 구성 요소를 확인합니다.

  ![시스템 평가](media/installer-image3.png)

5. 그런 다음 개인 정보 및 라이선스 조건에 동의하라는 경고 대화 상자가 표시됩니다. **계속** 단추를 눌러 조건에 동의합니다.

  ![라이선스 대화 상자](media/installer-image4.png)

6. 설치 관리자가 누락되어 다운로드 및 설치해야 하는 필수 구성 요소 목록을 표시합니다. 여기서 다운로드할 제품을 선택합니다.

  ![항목 선택](media/installer-image5.png)

  이 설치 화면에는 각 개별 구성 요소의 버전 및 크기가 표시됩니다. 각 구성 요소를 클릭하여 해당 구성 요소에 대한 종속성 목록을 표시하거나(Android), 다운로드한 추가 패키지를 확인하거나(.NET Core), 필요한 추가 응용 프로그램을 볼 수 있습니다(iOS 및 macOS).

  ![Android 추가 종속성](media/installer-image6.png)

7. 선택 항목에 만족할 경우 **설치 및 업데이트** 단추를 선택하여 설치 프로세스를 시작합니다.

8. 설치 관리자가 선택한 항목의 다운로드 및 설치 프로세스를 시작합니다.

  ![설치 시작](media/installer-image7.png)

  ![Xamarin.Mac 다운로드](media/installer-image8.png)

  ![설치 완료](media/installer-image9.png)

9. 설치를 완료하는 데 필요한 개별 구성 요소에 대한 필수 사용 권한을 상승하라는 메시지가 표시될 수 있습니다. 여기서 관리자 자격 증명을 입력하여 설치 프로세스를 계속합니다.

  ![사용 권한을 입력하여 설치 관리자 계속 진행](media/installer-image10.png)

10. 설치가 완료되면 **시작**을 눌러 Visual Studio에서 앱 개발을 시작할 수 있습니다.

  ![Visual Studio를 엽니다.](media/installer-image11.png)

> [!NOTE]
원래 설치 중 #6단계에서 선택 취소하여 플랫폼 또는 도구를 설치하지 않도록 선택한 경우 나중에 구성 요소를 추가하려면 [설치 관리자](https://www.visualstudio.com/vs/)를 다시 실행해야 합니다.

