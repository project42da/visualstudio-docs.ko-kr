---
title: "다중 파일 어셈블리 구성 요소 &#39;component_filename&#39;을(를) &#39;destination_filename&#39; 파일에 복사할 수 없습니다. &lt;reason.&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.tasklisterror.cannotcopyscattercomponent"
ms.assetid: 22f851fc-431b-4cdf-9de1-3a29727fa1e6
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 다중 파일 어셈블리 구성 요소 &#39;component_filename&#39;을(를) &#39;destination_filename&#39; 파일에 복사할 수 없습니다. &lt;reason.&gt;
지정된 구성 요소가 bin 디렉터리에 복사되지 않았습니다.  
  
 일부 어셈블리는 여러 파일로 구성됩니다. 이 진단은 다중 어셈블리에 속하는 파일이 실행 디렉터리에 복사될 수 없을 때마다 표시됩니다.  
  
 실패에는 여러 가지 이유가 있습니다. 예를 들어, 디스크 공간이 부족하거나 경로 길이에 대한 MAX\_PATH 제한에 도달했을 수 있습니다. 또한, 복사되지 않는 구성 요소가 어쩌면 Visual Studio 프로세스에 의해 사용되고 있을 수 있습니다.  
  
 **이 오류를 해결하려면**  
  
-   여유 디스크 공간이 충분한지 확인합니다.  
  
-   프로젝트를 경로 길이가 현재 프로젝트 폴더의 경로 길이보다 짧은 폴더로 이동합니다.  
  
-   출력 디렉터리를 절대 경로 길이가 더 짧은 폴더로 변경합니다. 이것은 클라이언트\(비 웹\) 프로젝트에만 적용됩니다.  
  
-   [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]를 다시 시작합니다.  
  
## 참고 항목  
 [웹 응용 프로그램 디버깅: 오류 및 문제 해결](../debugger/debugging-web-applications-errors-and-troubleshooting.md)