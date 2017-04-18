---
title: "Visual Studio 관리자 가이드 | Microsoft 문서"
ms.custom: 
ms.date: 04/03/2017
ms.prod: visual-studio-dev15
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-install
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- network installation, Visual Studio
- administrator guide, Visual Studio
- installing Visual Studio, administrator guide
ms.assetid: 4af353f5-6cfd-4ebe-bcfb-f42306e451a0
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
ms.sourcegitcommit: af9699b63fdfb81a274affb78856817520c38b05
ms.openlocfilehash: fb7a87b720ad29252c602d9be5b958d8417ab93e
ms.lasthandoff: 04/03/2017

---
# <a name="visual-studio-administrator-guide-for-visual-studio-2017"></a>Visual Studio 2017용 Visual Studio 관리자 가이드

 각 대상 컴퓨터가 [최소 설치 요구 사항](https://www.visualstudio.com/en-us/productinfo/vs2017-system-requirements-vs)을 충족하기만 하면 Visual Studio를 네트워크에 배포할 수 있습니다.

 System Center 같은 소프트웨어를 통해 배포하든 아니면 배치 파일을 통해 배포하든 대개 다음 단계를 수행하게 됩니다.

1. 네트워크 위치에 [Visual Studio 제품 레이아웃 캐시](create-an-offline-installation-of-visual-studio.md)

2. 설치하려는 [워크로드 및 구성 요소 선택](workload-and-component-ids.md)

3. 선택한 항목 및 설치 제어를 위한 다른 명령줄 매개 변수를 사용하여 [설치 스크립트 빌드](use-command-line-parameters-to-install-visual-studio.md)

4. 필요에 따라 설치 스크립트의 일부로 [볼륨 라이선스 제품 키를 적용](automatically-apply-product-keys-when-deploying-visual-studio.md)하여 사용자가 소프트웨어를 별도로 활성화할 필요가 없도록 합니다.

5. 선택한 배포 기술을 사용하여 대상 개발자 워크스테이션의 이전 단계에서 생성된 스크립트를 실행합니다.

6. 1단계에서 사용한 명령을 정기적으로 실행하여 업데이트된 구성 요소를 추가하는 방법으로 네트워크 위치를 최신 업데이트로 갱신합니다.

> [!IMPORTANT]
>  네트워크 공유에서 설치하는 경우 소스 위치가 "기억"됩니다. 이는 클라이언트 컴퓨터 복구 시 클라이언트가 원래 설치된 네트워크 공유로 돌아가야 할 수도 있음을 의미합니다. 조직에서 Visual Studio 2017 클라이언트를 실행하는 예상 수명에 맞도록 네트워크 위치를 신중하게 선택합니다.

## <a name="tools"></a>도구

 클라이언트 컴퓨터에 설치된 Visual Studio 인스턴스를 검색 및 관리하는 데 사용할 수 있는 몇 가지 도구를 만들었습니다.

* [VSWhere](https://github.com/microsoft/vswhere): Visual Studio의 설치된 인스턴스에서 핵심 Visual Studio 도구의 위치를 찾는 데 도움이 되는 C++ 실행 파일입니다.
* [VSSetup.PowerShell](https://github.com/microsoft/vssetup.powershell): 설치 구성 API를 사용하여 Visual Studio의 설치된 인스턴스를 식별하는 PowerShell 스크립트입니다.
* [VS-Setup-Samples](https://github.com/microsoft/vs-setup-samples): 설치 구성 API를 사용하여 기존 설치를 쿼리하는 방법을 보여 주는 C# 및 C++ 샘플입니다.

뿐만 아니라 [설치 구성 API](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.setup.configuration.aspx)는 Visual Studio 인스턴스를 조회하기 위해 자신의 유틸리티를 빌드하려는 개발자를 위한 인터페이스를 제공합니다.

>[!TIP]
>Visual Studio 2017 설치에 대한 자세한 내용은 [Heath Stewart의 블로그 기사](https://blogs.msdn.microsoft.com/heaths/tag/vs2017/)를 참조하세요.


## <a name="see-also"></a>참고 항목
* [Visual Studio 2017 설치](install-visual-studio.md)
* [Visual Studio 2017용 오프라인 설치 관리자 만들기](create-an-offline-installation-of-visual-studio.md)
* [명령줄 매개 변수를 사용하여 Visual Studio 2017 설치](use-command-line-parameters-to-install-visual-studio.md)
* [Visual Studio 2017의 문제 보고](../ide/how-to-report-a-problem-with-visual-studio-2017.md)

