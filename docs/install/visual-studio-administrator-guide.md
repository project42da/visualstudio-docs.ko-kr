---
title: "Visual Studio 관리자 가이드 | Microsoft 문서"
ms.custom: 
ms.date: 05/06/2017
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
ms.translationtype: Human Translation
ms.sourcegitcommit: b5b496e0de0a12c9f52c944ef9e768c82d9be783
ms.openlocfilehash: c88a932beac964117ac2fd6ffe171bf4256ac706
ms.contentlocale: ko-kr
ms.lasthandoff: 05/08/2017

---
# <a name="visual-studio-2017-administrator-guide"></a>Visual Studio 2017 관리자 가이드

엔터프라이즈 환경에서는 일반적으로 시스템 관리자가 네트워크 공유 또는 시스템 관리 소프트웨어를 사용하여 최종 사용자에게 설치를 배포합니다. Visual Studio 설치 엔진은 엔터프라이즈 배포를 지원하고, 시스템 관리자가 네트워크 설치 위치를 만들고, 설치 기본값을 미리 구성하고, 설치하는 동안 제품 키를 배포하고, 출시 후 제품 업데이트를 관리할 수 있도록 구성되었습니다. 이 관리자 가이드에서는 일반적인 네트워크 환경의 엔터프라이즈 배포에 대한 시나리오 기반 지침을 제공합니다.

## <a name="steps-for-deploying-visual-studio-2017-in-an-enterprise-environment"></a>엔터프라이즈 환경에 Visual Studio 2017을 배포하는 단계

각 대상 컴퓨터가 [최소 설치 요구 사항](https://www.visualstudio.com/en-us/productinfo/vs2017-system-requirements-vs)을 충족하면 클라이언트 워크스테이션에 Visual Studio 2017을 배포할 수 있습니다. System Center 같은 소프트웨어를 통해 배포하든 아니면 배치 파일을 통해 배포하든 대개 다음 단계를 수행하게 됩니다.

1. 네트워크 위치에 [Visual Studio 제품 파일이 포함된 네트워크 공유를 만듭니다](create-a-network-installation-of-visual-studio.md).

2. 설치할 [워크로드 및 구성 요소를 선택](workload-and-component-ids.md)합니다.

3. 기본 설치 옵션이 포함된 [지시 파일을 만듭니다](automated-installation-with-response-file.md). 또는 명령줄 매개 변수를 사용하여 설치를 제어하는 [설치 스크립트를 빌드](use-command-line-parameters-to-install-visual-studio.md)합니다.

4. 필요에 따라 사용자가 소프트웨어를 별도로 활성화할 필요가 없도록 설치 스크립트의 일부로 [볼륨 라이선스 제품 키를 적용](automatically-apply-product-keys-when-deploying-visual-studio.md)합니다.

5. 네트워크 레이아웃을 업데이트하여 [제품 업데이트가 최종 사용자에게 전달되는 시점을 제어](controlling-updates-to-visual-studio-deployments.md)합니다.

6. 필요에 따라 레지스트리 키를 설정하여 [클라이언트 워크스테이션에 캐시되는 항목을 제어](set-defaults-for-enterprise-deployments.md)합니다.

7. 선택한 배포 기술을 사용하여 대상 개발자 워크스테이션의 이전 단계에서 생성된 스크립트를 실행합니다.

8. 1단계에서 사용한 명령을 정기적으로 실행하여 업데이트된 구성 요소를 추가하는 방법으로 [네트워크 위치를 최신 업데이트로 갱신](update-a-network-installation-of-visual-studio.md)합니다.

> [!IMPORTANT]
> 네트워크 공유에서 설치하는 경우 소스 위치가 "기억"됩니다. 이는 클라이언트 컴퓨터 복구 시 클라이언트가 원래 설치된 네트워크 공유로 돌아가야 할 수도 있음을 의미합니다. 조직에서 Visual Studio 2017 클라이언트를 실행하는 예상 수명에 맞도록 네트워크 위치를 신중하게 선택합니다.

## <a name="tools"></a>도구
클라이언트 컴퓨터에 설치된 [Visual Studio 인스턴스를 검색 및 관리](tools-for-managing-visual-studio-instances.md)하는 데 사용할 수 있는 몇 가지 도구를 만들었습니다.

> [!TIP]
> 관리자 가이드의 문서 외에 Visual Studio 2017 설치에 대한 좋은 정보 출처는 [Heath Stewart의 블로그](https://blogs.msdn.microsoft.com/heaths/tag/vs2017/)입니다.

## <a name="see-also"></a>참고 항목
* [Visual Studio 2017 설치](install-visual-studio.md)
* [오프라인 환경에서 Visual Studio 설치](install-visual-studio-in-offline-environment.md)
* [명령줄 매개 변수를 사용하여 Visual Studio 2017 설치](use-command-line-parameters-to-install-visual-studio.md)
  * [명령줄 매개 변수 예](command-line-parameter-examples.md)
* [Visual Studio 2017의 문제 보고](../ide/how-to-report-a-problem-with-visual-studio-2017.md)

