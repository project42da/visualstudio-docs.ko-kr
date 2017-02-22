---
title: "DEBUG_CUSTOM_VIEWER | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "DEBUG_CUSTOM_VIEWER"
helpviewer_keywords: 
  - "DEBUG_CUSTOM_VIEWER 구조"
ms.assetid: 8e0ef3f0-0107-48e8-a037-6e52b4c4ed9d
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# DEBUG_CUSTOM_VIEWER
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

사용자 지정 뷰어를 식별 하는 구조 또는 시각화를 입력 합니다.  
  
## 구문  
  
```cpp  
typedef struct tagDEBUG_CUSTOM_VIEWER {  
   DWORD dwID;  
   BSTR  bstrMenuName;  
   BSTR  bstrDescription;  
   GUID  guidLang;  
   GUID  guidVendor;  
   BSTR  bstrMetric;  
} DEBUG_CUSTOM_VIEWER;  
```  
  
```c#  
public struct DEBUG_CUSTOM_VIEWER {  
   public uint   dwID;  
   public string bstrMenuName;  
   public string bstrDescription;  
   public Guid   guidLang;  
   public Guid   guidVendor;  
   public string bstrMetric;  
};  
```  
  
## Members  
 dwID  
 여러 보는 사람이 나 하나에 의해 구현 되는 시각화 도우미를 구별 하기 위해 ID `GUID`.  
  
 bstrMenuName  
 드롭다운 메뉴에 표시 될 텍스트입니다.  
  
 bstrDescription  
 형식 시각화 도우미 \(null 값 사용 되지 않는 경우 이어야 합니다\) 또는 사용자 지정 뷰어 설명입니다.  
  
 guidLang  
 언어 제공 식 계산기입니다.  
  
 guidVendor  
 공급 업체 제공 식 계산기입니다.  
  
 bstrMetric  
 미터법을 사용자 지정 뷰어 또는 형식 시각화 도우미 `CLSID` 에 저장 됩니다.  
  
## 설명  
 호출 하 여이 구조체의 목록이 반환 됩니다 있는 [GetCustomViewerList](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewerlist.md) 메서드 \(및 더 나아가 [GetCustomViewerList](../../../extensibility/debugger/reference/ieevisualizerservice-getcustomviewerlist.md) 메서드\).  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [GetCustomViewerList](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewerlist.md)   
 [GetCustomViewerList](../../../extensibility/debugger/reference/ieevisualizerservice-getcustomviewerlist.md)