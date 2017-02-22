---
title: "IDebugBinder3::GetEEService | Microsoft Docs"
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
  - "IDebugBinder3::GetEEService"
helpviewer_keywords: 
  - "IDebugBinder3::GetEEService 메서드"
ms.assetid: eb07aa40-8cd9-4a52-a4c7-4affd2307a01
caps.latest.revision: 12
caps.handback.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugBinder3::GetEEService
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 메서드는 요청한 서비스를 반환합니다.  
  
## 구문  
  
```cpp  
HRESULT GetEEService(  
   [in] GUID        vendor,  
   [in] GUID        language,  
   [in] GUID        iid,  
   [out] IUnknown** ppService  
);  
```  
  
```c#  
Int GetEEService(  
   Guid       vendor,  
   Guid       language,  
   Guid       iid,  
   out object ppService  
);  
```  
  
#### 매개 변수  
 `vendor`  
 \[in\] `GUID` \(null 값이 허용 가능한 서버\)의 공급 업체입니다.  
  
 `language`  
 \[in\] `GUID` \(null 값은 허용\) 언어.  
  
 `iid`  
 \[in\] `IID` 서비스를 얻을 수 있습니다.  
  
 `ppService`  
 \[out\] 요청 된 서비스 인터페이스입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 통과 `IID` 에 [IEEVisualizerServiceProvider](../../../extensibility/debugger/reference/ieevisualizerserviceprovider.md) 인터페이스 \(`IID_IEEVisualizerServiceProvider`\) 형식을 시각화 도우미 서비스를 사용할 수 있는지 확인 합니다.  식 계산기에서 얻을 수 있는 경우는 [IEEVisualizerService](../../../extensibility/debugger/reference/ieevisualizerservice.md) 인터페이스 형식을 시각화 도우미를 지원 합니다.  자세한 내용은 [시각화 및 데이터 보기](../../../extensibility/debugger/visualizing-and-viewing-data.md)를 참조하십시오.  
  
## 참고 항목  
 [IDebugBinder3](../../../extensibility/debugger/reference/idebugbinder3.md)   
 [IEEVisualizerServiceProvider](../../../extensibility/debugger/reference/ieevisualizerserviceprovider.md)   
 [IEEVisualizerService](../../../extensibility/debugger/reference/ieevisualizerservice.md)   
 [시각화 및 데이터 보기](../../../extensibility/debugger/visualizing-and-viewing-data.md)