---
title: "실험적 인스턴스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "실험적 빌드"
  - "Vspackage를 실험적 빌드"
  - "VSIP, 실험적 빌드"
ms.assetid: ead0df4e-6f88-4b42-9297-581b7902f050
caps.latest.revision: 36
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 36
---
# 실험적 인스턴스
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

변경할 수는 테스트 되지 않은 응용 프로그램에서 Visual Studio 개발 환경, 보호 하는 VSSDK 실험 하는 데 사용할 수 있는 실험적 공간을 제공 합니다. 일반적으로 Visual Studio를 사용 하 여 새 응용 프로그램을 개발 하지만이 실험적 인스턴스를 사용 하 여 실행 합니다.  
  
 VSIX 패키지에 있는 모든 응용 프로그램이 디버그 모드에서 Visual Studio 실험적 인스턴스를 시작 합니다.  
  
 특정 솔루션 외부 Visual Studio의 실험적 인스턴스를 시작 하려면 명령 창에서 다음 명령을 실행 합니다.  
  
 "*\< visual studio 설치 경로 \>*\\Common7\\IDE\\devenv.exe" RootSuffix Exp  
  
> [!NOTE]
>  실험적 인스턴스에서 레지스트리의 아래에 기록 되는 `<version number>Exp` 및 `<version number>Exp_Config` 노드. 예를 들어 Visual Studio 2015 실험적 레지스트리 영역이  
>   
>  `HKCU\Software\Microsoft\VisualStudio\14.0Exp` 및 `HKCU\Software\Microsoft\VisualStudio\14.0Exp_Config`  
  
 개발 하는 동안 실험적 인스턴스에서 확장 프로그램을 실행 하는 것이 좋습니다. 확장을 배포 하는 경우 개발 인스턴스에서 실행 됩니다. 응용 프로그램을 등록 하는 방법에 대 한 자세한 내용은 참조 [Vspackage를 등록 하는 중](../extensibility/internals/registering-vspackages.md)합니다.