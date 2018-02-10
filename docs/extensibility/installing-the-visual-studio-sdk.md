---
title: "Visual Studio SDK 설치 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c730edb6-5099-4c16-85a8-08def09f1455
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 8a5a4721eea178e4a9ab5766760ccf1405589684
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2018
---
# <a name="installing-the-visual-studio-sdk"></a>Visual Studio SDK 설치
Visual Studio SDK는 Visual Studio 설치 프로그램에서 선택적 기능. 또한 VS SDK를 나중에 설치할 수 있습니다.  
  
## <a name="installing-the-visual-studio-sdk-as-part-of-a-visual-studio-installation"></a>Visual Studio 설치의 일부로 Visual Studio SDK 설치  
 VSSDK를 Visual Studio 설치에 포함 하려는 경우 설치 해야는 **Visual Studio 확장 개발** 작업에서 **다른 도구 집합**합니다. 필요한 필수 구성 요소 뿐만 아니라 Visual Studio SDK를 설치 합니다. 선택 하 여 설치를 추가로 튜닝할 수 보거나 요약에서 구성 요소. 
  
## <a name="installing-the-visual-studio-sdk-after-installing-visual-studio"></a>Visual Studio를 설치한 후 Visual Studio SDK를 설치 합니다.  
 Visual Studio 설치를 완료 한 후 Visual Studio SDK를 설치 하려는 경우 Visual Studio 설치 관리자를 다시 실행 하 고 선택 된 **Visual Studio 확장 개발** 작업 합니다.  
  
## <a name="installing-the-visual-studio-sdk-from-a-solution"></a>솔루션에서 Visual Studio SDK 설치  
 VSSDK를 먼저 설치 하지 않고 확장성 프로젝트와 솔루션을 열 경우 솔루션 탐색기 위에 강조 표시 된 정보 표시줄에 나타납니다. 다음과 같은 같아야 합니다.  
  
 ![SolutionExplorerInstall](../extensibility/media/solutionexplorerinstall.png "SolutionExplorerInstall")  
  
## <a name="installing-the-visual-studio-sdk-from-the-command-line"></a>명령줄에서 Visual Studio SDK 설치  
모든 Visual Studio 작업 또는 구성 요소와 마찬가지로 명령줄에서 항목을 설치할 수 있습니다. 참조 [명령줄 매개 변수를 사용 하 여 Visual Studio 설치](../install/use-command-line-parameters-to-install-visual-studio.md) 적절 한 명령줄 스위치와 작업 또는 구성 요소 식별자를 확인 하는 방법에 대 한 자세한 내용은 합니다.
  
 참고가 설치 된 버전의 Visual Studio와 일치 하는 Visual Studio 설치 관리자를 사용 해야 합니다. 예를 들어 컴퓨터에 설치 된 Visual Studio Enterprise를 사용 하도록 설정한 경우에 Visual Studio Enterprise (vs_enterprise.exe) 설치 관리자를 실행 해야 합니다.