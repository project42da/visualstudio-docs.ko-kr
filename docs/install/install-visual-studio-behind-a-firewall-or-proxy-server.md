---
title: "방화벽 또는 프록시 서버 뒤에 Visual Studio 설치 | Microsoft Docs"
description: 
ms.custom: 
ms.date: 07/18/2017
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
- list of domains, locations, URLs
ms.assetid: 
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: ddbbda1069749e2ce685507d55a070f1dec27c17
ms.openlocfilehash: 48fd143f917d6e13c18f6913bea625b2e8cf5ce8
ms.contentlocale: ko-kr
ms.lasthandoff: 07/19/2017

---
# <a name="install-visual-studio-behind-a-firewall-or-proxy-server"></a>방화벽 또는 프록시 서버 뒤에 Visual Studio 설치

Visual Studio 설치 관리자는 다양한 도메인 및 해당 다운로드 서버에서 파일을 다운로드합니다. 이 페이지에는 배포 스크립트에서 신뢰할 수 있는 도메인 URL을 “허용 목록”으로 나열합니다.

사용자 환경에 대해 가능한 경우 HTTP 및 HTTPS 프로토콜과 함께 다음 도메인을 추가해 보세요.

## <a name="microsoft-domains"></a>Microsoft 도메인
| 도메인 | 용도 |
| ------ | ------- |
| go.microsoft.com | 설치 URL 확인 |
| aka.ms | 설치 URL 확인 |
| download.visualstudio.microsoft.com | 설치 패키지 다운로드 위치 |
| download.microsoft.com | 설치 패키지 다운로드 위치 |
| download.visualstudio.com | 설치 패키지 다운로드 위치 |
| dl.xamarin.com | 설치 패키지 다운로드 위치 |
| visualstudiogallery.msdn.microsoft.com | Visual Studio 확장 다운로드 위치 |
| www.visualstudio.com | 문서 위치 |
| msdn.microsoft.com | 문서 위치 |
| www.microsoft.com | 문서 위치 |

## <a name="non-microsoft-domains"></a>타사 도메인
| 도메인 | 이러한 워크로드 설치 |
| ------ | ------- |
| archive.apache.org |  JavaScript를 사용한 모바일 개발 <br />(Cordova) |
| cocos2d-x.org | C++를 사용한 게임 개발 <br />(Cocos) |
| download.epicgames.com | C++를 사용한 게임 개발 <br />(Unreal Engine) |
| download.oracle.com | JavaScript를 사용한 모바일 개발 <br />(Java SDK) <br /><br />.NET을 사용한 모바일 개발 <br />(Java SDK) |
| download.unity3d.com | Unity를 사용한 게임 개발 <br />(Unity) |
| netstorage.unity3d.com | Unity를 사용한 게임 개발 <br /> (Unity) |
| dl.google.com | JavaScript를 사용한 모바일 개발 <br />(Android SDK 및 NDK, 에뮬레이터) <br /><br />.NET을 사용한 모바일 개발 <br />(Android SDK 및 NDK, 에뮬레이터) |
| www.incredibuild.com | C++를 사용한 게임 개발 <br />(IncrediBuild) |
| incredibuildvs2017i.azureedge.net | C++를 사용한 게임 개발 <br />(IncrediBuild) |
| www.python.org | Python 개발 <br />(Python) <br /><br />데이터 과학 및 분석 응용 프로그램 <br />(Python) |

## <a name="see-also"></a>참고 항목
* [Visual Studio 2017 설치](install-visual-studio.md)
* [Visual Studio 관리자 가이드](visual-studio-administrator-guide.md)
  * [명령줄 매개 변수를 사용하여 Visual Studio 2017 설치](use-command-line-parameters-to-install-visual-studio.md)
    * [명령줄 매개 변수 예](command-line-parameter-examples.md)
    * [워크로드 및 구성 요소 ID 참조](workload-and-component-ids.md)
  * [Visual Studio의 네트워크 기반 설치 만들기](create-a-network-installation-of-visual-studio.md)
    * [오프라인 환경에서 Visual Studio 설치에 대한 특별 고려 사항](install-visual-studio-in-offline-environment.md)
  * [지시 파일을 사용하여 Visual Studio 자동화](automated-installation-with-response-file.md)
  * [Visual Studio를 배포할 때 제품 키를 자동으로 적용](automatically-apply-product-keys-when-deploying-visual-studio.md)
  * [Visual Studio의 엔터프라이즈 배포에 대한 기본값 설정](set-defaults-for-enterprise-deployments.md)
  * [패키지 캐시를 사용하지 않도록 설정 또는 이동](disable-or-move-the-package-cache.md)
  * [Visual Studio의 네트워크 기반 설치 업데이트](update-a-network-installation-of-visual-studio.md)
  * [Visual Studio 배포에 대한 업데이트 제어](controlling-updates-to-visual-studio-deployments.md)
  * [Visual Studio 인스턴스 검색 및 관리 도구](tools-for-managing-visual-studio-instances.md)
  * [Visual Studio 2017의 문제 보고](../ide/how-to-report-a-problem-with-visual-studio-2017.md)

