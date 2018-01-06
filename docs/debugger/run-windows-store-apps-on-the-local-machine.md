---
title: "UWP 앱에서 로컬 컴퓨터에서 실행 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: e42a21a8-6423-4caf-b4dc-72b263e76019
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: uwp
ms.openlocfilehash: 63cb81c9bc168ad0bda8d675c0bf0bbde3759eff
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="run-uwp-apps-on-the-local-machine"></a>UWP 앱에서 로컬 컴퓨터에서 실행
![Windows에만 적용](../debugger/media/windows_only_content.png "windows_only_content")  
  
 디버깅, 테스트 또는 UWP 앱에서 성능 분석 실행을 하려면 실행할 수 있습니다 앱 같은 컴퓨터에서 Visual Studio를 호스트 하 합니다. 장치의 디스플레이에서 터치 기능을 사용할 수 있으면 앱의 전체 기능을 실행할 수 있습니다. 그렇지 않으면 마우스 및 키보드 제스처만 사용할 수 있습니다.  
  
##  <a name="BKMK_How_to_run_on_a_local_machine"></a>로컬 컴퓨터에서 실행 하는 방법  
 로컬 컴퓨터에서 앱을 실행 하려면 선택 **로컬 컴퓨터** 디버거 디버깅 시작 단추 옆의 드롭다운 목록에서 **표준** 도구 모음입니다.  
  
 ![로컬 컴퓨터에서 실행](../debugger/media/vsrun_f5_local.png "VSRUN_F5_Local")  
  
 표시 되지 않는 경우는 **표준** 도구 모음을 클릭는 **보기** 메뉴에서 **도구 모음**, 클릭 하 고 **표준**합니다.  
  
 드롭다운 목록에서 선택한 항목은 프로젝트 속성 파일에서 유지되고 기본 실행 대상이 됩니다.  
  
 또한 프로젝트 속성 파일에서 직접 실행 대상을 설정할 수 있습니다. 프로젝트 이름을 마우스 오른쪽 단추로 클릭 **솔루션 탐색기** 선택한 후 **속성**합니다. 다음 작업 중 하나를 수행합니다.  
  
-   C# 및 Visual Basic 프로젝트에서 클릭 **디버그** 선택한 후 **로컬 컴퓨터** 에서 **대상 장치** 드롭 다운 목록입니다.  
  
     ![&#35; 및 Visual Basic 프로젝트 속성 페이지](../debugger/media/vsrun_cs_vb_projprop_local.png "VSRUN_CS_VB_ProjProp_Local")  
  
-   C + + 및 JavaScript 프로젝트에서 확장 하 고는 **구성 속성** 노드를 클릭 하 여 **디버깅**를 선택한 후 **로컬 디버거** 에서 **디버거 시작 하려면** 목록입니다.  
  
     ![C# 43; &#43; JavaScript 프로젝트 속성 페이지 및](../debugger/media/vsrun_cpp_js_projprop_local.png "VSRUN_CPP_JS_ProjProp_Local")  