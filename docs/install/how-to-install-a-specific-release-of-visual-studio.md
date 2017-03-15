---
title: "방법: Visual Studio의 특정 릴리스 설치 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-install"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "특정 릴리스, Visual Studio 설치"
ms.assetid: d69ad0f8-f0a0-438e-a0ef-777c4868f139
caps.latest.revision: 20
caps.handback.revision: 11
author: "TerryGLee"
ms.author: "tglee"
manager: "ghogen"
---
# 방법: Visual Studio의 특정 릴리스 설치
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

선택적 기능의 최적화된 최신 버전을 사용할 수 있도록 Visual Studio 설치가 종종 업데이트됩니다.  하지만 이전 릴리스의 Visual Studio 2015\(예: iOS 지원을 포함하는 Visual Studio 서전 업데이트 1 릴리스\)를 설치하려면 Visual Studio 설치에서 해당 기능 매니페스트 파일의 이전 버전을 사용하도록 강제해야 합니다. 이 문서에서는 그렇게 하는 방법을 설명합니다.  
  
## 현재 릴리스 설치  
 Visual Studio 2015 초기 릴리스 이후 설치 엔진은 1회, 매니페스트 파일은 5회 이상 업데이트되었습니다.  따라서 인터넷에 연결된 새 컴퓨터에서 [지금 Visual Studio 설치프로그램을 다운로드 및 실행](https://www.visualstudio.com/downloads/download-visual-studio-vs)하는 경우 설치 프로그램에서는 최신 제품 개선 사항과 선택적 기능 및 도구의 최신 버전을 포함하는 Visual Studio 2015 업데이트 1을 설치합니다.  
  
## 이전 릴리스 설치  
 ISO 이미지를 만들고 탑재하거나 직접 웹 설치 관리자를 다운로드하고 시작한 다음 .exe 파일에 명령줄 매개 변수\(예: \/CustomInstallPath, \/Full, \/InstallSelectableItems, \/NoRestart 등\)를 추가하여 Visual Studio 설치되는 방법을 제어할 수 있습니다.  
  
 다음 표에는 몇 가지 특정 시점 시나리오와 Enterprise Edition 웹 설치 관리자에 전달해야 하는 명령줄 매개 변수가 나와 있습니다. \(동일한 매개 변수가 Community 또는 Professional 버전 웹 설치 관리자에도 적용됩니다.\)  
  
|Visual Studio 2015 버전|실행할 버전|사용할 명령줄|설치 프로그램에서 수행하는 작업|  
|---------------------------|------------|-------------|-----------------------|  
|Visual Studio Enterprise\(최신 공개 릴리스\)|Visual Studio Enterprise 업데이트 1\([VisualStudio.com](https://www.visualstudio.com/en-us/products/vs-2015-product-editions.aspx)에서 이용 가능\)|`vs_enterprise.exe` **Note:**  이 설치의 기본 동작에서는 최신 선택적 기능을 제공하므로 명령줄 매개 변수가 필요하지 않습니다.|Visual Studio 설치 프로그램에서 최신 feed.xml를 사용하고 최신 파일을 설치합니다.|  
|Visual Studio Enterprise\(원래 RTM이지만 업데이트 1 이전의 업데이트 포함\)|Visual Studio Enterprise RTM\([MSDN 구독자 다운로드 페이지](https://msdn.microsoft.com/en-us/subscriptions/downloads/)에서 이용 가능\)|`vs_enterprise.exe /OverrideFeedURI https://download.microsoft.com/download/3/6/1/36188D5F-479F-4A46-BF55-6AE5928D1EBB/20151102.3/enu/feed.xml`|Visual Studio 설치 프로그램에서 업데이트 1 출시 전의 최신 feed.xml를 사용합니다.|  
|Visual Studio Enterprise 업데이트 1\(업데이트 1 세대의 추가 업데이트를 포함하지 않는 원래 업데이트 1\)|Visual Studio Enterprise 업데이트 1\([MSDN 구독자 다운로드 페이지](https://msdn.microsoft.com/en-us/subscriptions/downloads/)에서 이용 가능\)|`vs_enterprise.exe /OverrideFeedURI https://download.microsoft.com/download/3/2/A/32A1974F-D236-43C1-8981-97DDCBAEF14A/20151201.1/enu/feed.xml`|Visual Studio 설치 프로그램에서 업데이트 1에서 제공된 feed.xml을 사용합니다.|  
|Visual Studio Enterprise\(업데이트를 포함하지 않는 원래 RTM\)|Visual Studio Enterprise RTM\([MSDN 구독자 다운로드 페이지](https://msdn.microsoft.com/en-us/subscriptions/downloads/)에서 이용 가능\)|`vs_enterprise.exe /OverrideFeedURI https://download.microsoft.com/download/5/7/B/57BF5016-E4F0-4EB5-BE27-2BFA87E7723F/20150713.1/enu/feed.xml`|Visual Studio 설치 프로그램에서 RTM에서 제공된 feed.xml을 사용합니다.|  
  
> [!IMPORTANT]
>  사용하려는 언어에 따라 "enu"\(영어\)를 다음 값 중 하나로 바꾸세요.  
>   
>  -   chs\(중국어 간체\)  
> -   cht\(중국어 번체\)  
> -   csy\(체코어\)  
> -   deu\(독일어\)  
> -   esn\(스페인어\)  
> -   fra\(프랑스어\)  
> -   ita\(이탈리아어\)  
> -   jpa\(일본어\)  
> -   kor\(한국어\)  
> -   plk\(폴란드어\)  
> -   ptb\(포르투갈어\)  
> -   rus\(러시아어\)  
> -   trk\(터키어\)  
  
## 참고 항목  
 [Visual Studio 설치](../Topic/Installing%20Visual%20Studio%202015.md)