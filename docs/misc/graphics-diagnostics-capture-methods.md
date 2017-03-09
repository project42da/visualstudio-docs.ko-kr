---
title: "그래픽 진단 캡처 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ea21995d-0241-412e-8f62-600c3794247f
caps.latest.revision: 2
caps.handback.revision: 2
ms.author: "mithom"
manager: "douge"
---
# 그래픽 진단 캡처 메서드
여기에 소개하는 내용을 삽입합니다.  
  
## 캡처 모드  
 [!INCLUDE[win81](../debugger/includes/win81_md.md)]에서 DirectX 11.2 런타임은 그래픽 진단과 같은 디버깅 도구를 대신하여 그래픽 정보를 내부적으로 캡처할 수 있습니다.이를 *강력한 캡처*라고 합니다.  DirectX 런타임에 이러한 지원이 추가되기 전에 그래픽 정보는 완료된 DirectX에 대한 호출을 전달하기 전에 인수 및 기타 정보를 기록하도록 특정 DirectX 함수 호출을 해석하여 캡처되었습니다. 이러한 캡처를 *레거시 캡처*라고 합니다 .  
  
 DirectX 런타임은 [!INCLUDE[win81](../debugger/includes/win81_md.md)]에서 그래픽 정보 캡처를 전적으로 담당하므로 DirectX 11.2를 지원하기 위해 레거시 캡처를 업데이트할 필요가 없습니다. 따라서 레거시 캡처는 사용되지 않습니다.  그러나 DirectX 11.2 런타임이 [!INCLUDE[win81](../debugger/includes/win81_md.md)] 이전 Windows 버전을 지원하지 않으므로 [!INCLUDE[vs_dev12](../data-tools/includes/vs_dev12_md.md)]에서는 [!INCLUDE[win8](../debugger/includes/win8_md.md)] 및 [!INCLUDE[win7](../debugger/includes/win7_md.md)]용 앱에 대해서는 레거시 캡처를 계속해서 지원합니다.  
  
 두 방법 다 유사한 정보를 기록하지만 그래픽 정보 캡처 방법이나 그래픽 진단 도구 사용 방법을 변경하지는 않습니다.  
  
### 강력한 캡처  
 강력한 캡처는 [!INCLUDE[vs_dev12](../data-tools/includes/vs_dev12_md.md)], [!INCLUDE[win81](../debugger/includes/win81_md.md)] 및 Windows Phone 8.1에서 [!INCLUDE[winblue_winrt_2](../debugger/includes/winblue_winrt_2_md.md)] 그래픽 진단을 지원합니다.  또한 DirectX 10.0~DirectX 11.2를 지원하고 새 Direct3D 11.2 기능에 대한 그래픽 정보\(예: 타일식 리소스\)를 캡처할 수 있습니다.  그러나 Direct3D 11.2 기능 중 일부는 지원하지 않습니다. 예를 들어 HLSL 셰이더 연결 기능을 사용하여 만든 HLSL 셰이더는 디버깅할 수 없습니다.  강력한 캡처는 새 캡처 API를 사용하여 프로그래밍 캡처 시나리오를 지원합니다.  
  
### 레거시 캡처  
 레거시 캡처는 [!INCLUDE[vs_dev12](../data-tools/includes/vs_dev12_md.md)], Windows RT 8 및 [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)]에서 [!INCLUDE[win8](../debugger/includes/win8_md.md)] 및 [!INCLUDE[win7](../debugger/includes/win7_md.md)] 그래픽 진단을 지원합니다.  또한 DirectX 10.0~DirectX 11.1을 지원합니다.  레거시 캡처는 Direct3D 11.2 기능을 전혀 지원하지 않으므로 강력한 캡처를 사용할 수 없는 시나리오를 제외하고는 사용되지 않습니다.  레거시 캡처는 `vsgcapture.h` 헤더 파일에 정의된 캡처 API를 사용하여 프로그래밍 캡처 시나리오를 지원합니다.  이러한 종류의 프로그래밍 캡처 또한 강력한 캡처를 사용하지 않는 시나리오를 제외하고는 사용되지 않습니다.  
  
## 참고 항목  
 [그래픽 정보 캡처](../debugger/capturing-graphics-information.md)   
 [연습: 그래픽 정보 캡처](../debugger/walkthrough-capturing-graphics-information.md)