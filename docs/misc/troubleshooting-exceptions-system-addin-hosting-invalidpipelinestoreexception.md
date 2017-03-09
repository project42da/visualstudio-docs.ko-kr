---
title: "예외 문제 해결: System.AddIn.Hosting.InvalidPipelineStoreException | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "InvalidPipelineStoreException 예외"
  - "System.AddIn.Hosting.InvalidPipelineStoreException 예외"
ms.assetid: d12556bc-5cfd-481c-a27b-46ee2571e646
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.AddIn.Hosting.InvalidPipelineStoreException
디렉터리가 없고 사용자에게 파이프라인 루트 경로 또는 추가 기능 경로에 액세스할 수 있는 권한이 없는 경우 <xref:System.AddIn.Hosting.InvalidPipelineStoreException> 예외가 throw됩니다.  
  
## 설명  
 <xref:System.IO.DirectoryNotFoundException>과 달리 이 예외는 경로 정보를 제공하지 않습니다. 따라서 악의적인 사용자가 고의로 잘못된 경로를 지정하고 실제 경로를 확인하기 위해 예외를 통해 반환되는 정보를 사용하는 것을 막을 수 있습니다.  
  
 이 예외는 추가 기능 및 파이프라인 정보의 저장소를 빌드 및 업데이트하는 <xref:System.AddIn.Hosting.AddInStore.FindAddIns%2A>, <xref:System.AddIn.Hosting.AddInStore.Rebuild%2A>, <xref:System.AddIn.Hosting.AddInStore.RebuildAddIns%2A>, <xref:System.AddIn.Hosting.AddInStore.Update%2A> 및 <xref:System.AddIn.Hosting.AddInStore.UpdateAddIns%2A> 검색 메서드에 의해 throw됩니다.  
  
## 참고 항목  
 <xref:System.AddIn.Hosting.InvalidPipelineStoreException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)