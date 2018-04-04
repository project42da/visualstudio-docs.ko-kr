---
title: Visual Studio를 배포할 때 제품 키를 자동으로 적용 | Microsoft Docs
ms.custom: ''
ms.date: 08/14/2017
ms.reviewer: tims
ms.suite: ''
ms.technology:
- vs-acquisition
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: d79260be-6234-4fd3-89b5-a9756b4a93c1
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1e9bfd9f72162d354d7e606d65146f602393d286
ms.sourcegitcommit: efd8c8e0a9ba515d47efcc7bd370eaaf4771b5bb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/03/2018
---
# <a name="automatically-apply-product-keys-when-deploying-visual-studio"></a>Visual Studio를 배포할 때 제품 키를 자동으로 적용
Visual Studio의 배포를 자동화하는 데 사용되는 스크립트의 일부로 제품 키를 프로그래밍 방식으로 적용할 수 있습니다. Visual Studio의 설치 중이나 설치가 완료된 후에 장치에서 프로그래밍 방식으로 제품 키를 설정할 수 있습니다.

## <a name="apply-the-license-after-installation"></a>설치 후 라이선스 적용
 대상 컴퓨터에서 자동 모드로 `StorePID.exe` 유틸리티를 사용하여 설치된 Visual Studio 버전을 제품 키로 활성화할 수 있습니다. `StorePID.exe`는 다음 기본 위치에 Visual Studio 2017과 함께 설치되는 유틸리티 프로그램입니다. <br> `C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\IDE`

 System Center 에이전트나 관리자 권한 명령 프로그램을 사용하여 높은 권한으로 `StorePID.exe`를 실행합니다. 이어서 제품 키와 MPC(Microsoft 제품 코드)를 입력합니다.

>[!IMPORTANT]
> 제품 키에 대시를 포함해야 합니다.

 ```
 StorePID.exe [product key including the dashes] [MPC]
 ```

 다음 예제에서는 기본 위치에 설치한다고 가정하고 MPC가 08860이고 제품 키가 `AAAAA-BBBBB-CCCCC-DDDDDD-EEEEEE`인 Visual Studio 2017 Enterprise에 대한 라이선스를 적용하는 명령줄을 보여 줍니다.

 ```cmd
 "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\StorePID.exe" AAAAA-BBBBB-CCCCC-DDDDDD-EEEEEE 08860
 ```

 다음 표에는 Visual Studio의 각 버전에 대한 MPC 코드가 나와 있습니다.

| Visual Studio 버전                | MPC   |
|--------------------------------------|-------|
| Visual Studio Enterprise 2017        | 08860 |
| Visual Studio Professional 2017      | 08862 |
| Visual Studio Test Professional 2017 | 08866 |

`StorePID.exe`는 제품 키를 성공적으로 적용한 경우 0의 `%ERRORLEVEL%`을 반환합니다. 오류가 발생하는 경우 오류 조건에 따라 다음 코드 중 하나를 반환합니다.

| Error                     | 코드 |
|---------------------------|------|
| `PID_ACTION_SUCCESS`      | 0    |
| `PID_ACTION_NOTINSTALLED` | 1    |
| `PID_ACTION_INVALID`      | 2    |
| `PID_ACTION_EXPIRED`      | 3    |
| `PID_ACTION_INUSE`        | 4    |
| `PID_ACTION_FAILURE`      | 5    |
| `PID_ACTION_NOUPGRADE`    | 6    |

## <a name="get-support"></a>지원 받기
때로는 무엇인가 잘못될 수도 있습니다. Visual Studio 설치에 실패하는 경우에는 [Visual Studio 2017 설치 및 업그레이드 문제 해결](troubleshooting-installation-issues.md) 페이지를 참조하세요. 문제 해결 단계가 도움이 되지 않는 경우 라이브 채팅을 통해 Microsoft에 설치 지원을 문의할 수 있습니다(영어만 가능). 자세한 내용은 [Visual Studio 지원 페이지](https://www.visualstudio.com/vs/support/#talktous)를 참조하세요.

몇 가지 추가 지원 옵션은 다음과 같습니다.
* Visual Studio 설치 관리자와 Visual Studio IDE에 모두 표시되는 [문제 보고](../ide/how-to-report-a-problem-with-visual-studio-2017.md) 도구를 통해 Microsoft에 제품 문제를 보고할 수 있습니다.
* [UserVoice](https://visualstudio.uservoice.com/forums/121579)에서 Microsoft와 제품 제안을 공유할 수 있습니다.
* [Visual Studio 개발자 커뮤니티](https://developercommunity.visualstudio.com/)에서 제품 문제를 추적하고 질문을 하고 답을 찾을 수 있습니다.
* [Gitter 커뮤니티의 Visual Studio 관련 대화](https://gitter.im/Microsoft/VisualStudio)를 통해 Microsoft 및 다른 Visual Studio 개발자와 소통할 수도 있습니다.  (이 옵션을 사용하려면 [GitHub](https://github.com/) 계정이 필요합니다.)

## <a name="see-also"></a>참고 항목
 * [Visual Studio 설치](../install/install-visual-studio.md)
 * [Visual Studio의 오프라인 설치 만들기](../install/create-an-offline-installation-of-visual-studio.md)
