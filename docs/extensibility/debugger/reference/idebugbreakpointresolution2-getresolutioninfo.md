---
title: "IDebugBreakpointResolution2::GetResolutionInfo | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugBreakpointResolution2::GetResolutionInfo"
helpviewer_keywords: 
  - "IDebugBreakpointResolution2::GetResolutionInfo"
ms.assetid: 828cbdf6-b87d-4c45-be87-d87087b04a60
caps.latest.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 12
---
# IDebugBreakpointResolution2::GetResolutionInfo
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 중단점은 중단점 해상도 정보를 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetResolutionInfo(   
   BPRESI_FIELDS       dwFields,  
   BP_RESOLUTION_INFO* pBPResolutionInfo  
);  
```  
  
```c#  
int GetResolutionInfo(   
   enum BPRESI_FIELDS   dwFields,  
   BP_RESOLUTION_INFO[] pBPResolutionInfo  
);  
```  
  
#### 매개 변수  
 `dwFields`  
 \[in\] 플래그의 조합을 [BPRESI\_FIELDS](../../../extensibility/debugger/reference/bpresi-fields.md) 어떤 필드를 결정 하는 열거형의 `pBPResolutionInfo` 매개 변수는 데이터를 입력할 수 있습니다.  
  
 `pBPResolutionInfo`  
 \[out\] [BP\_RESOLUTION\_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md) 구조를 사용 하 여이 중단점에 대 한 정보가 입력 되어야 합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 예제  
 다음 예제는이 메서드에 대 한 간단한 구현 `CDebugBreakpointResolution` 를 노출 하는 개체는 [IDebugBreakpointResolution2](../../../extensibility/debugger/reference/idebugbreakpointresolution2.md) 인터페이스입니다.  
  
```  
HRESULT CDebugBreakpointResolution::GetResolutionInfo(  
   BPRESI_FIELDS dwFields,  
   BP_RESOLUTION_INFO* pBPResolutionInfo)  
{    
   HRESULT hr;    
  
   if (pBPResolutionInfo)    
   {    
      // Copy the specified fields of the request information from the class  
      // member variable to the local BP_RESOLUTION_INFO variable.    
      hr = CopyBP_RESOLUTION_INFO(m_bpResolutionInfo,  
                                  *pBPResolutionInfo,  
                                  dwFields);    
   }    
   else    
   {    
      hr = E_INVALIDARG;    
   }    
  
   return hr;    
}    
  
HRESULT CDebugBreakpointResolution::CopyBP_RESOLUTION_INFO(  
   BP_RESOLUTION_INFO& bpResSrc,  
   BP_RESOLUTION_INFO& bpResDest,  
   DWORD dwFields)    
{    
   HRESULT hr = S_OK;    
  
   // Start with a raw copy.    
   memcpy(&bpResDest, &bpResSrc, sizeof(BP_RESOLUTION_INFO));    
  
   // The fields in the destination is the result of the AND of  
   //  bpInfoSrc.dwFields and dwFields.    
   bpResDest.dwFields = dwFields & bpResSrc.dwFields;    
  
   // Fill in the bp location information if the BPRESI_BPRESLOCATION  
   //  flag is set in BPRESI_FIELDS.    
   if (IsFlagSet(bpResDest.dwFields, BPRESI_BPRESLOCATION))    
   {    
      // Switch based on the BP_TYPE.     
      switch (bpResSrc.bpResLocation.bpType)    
      {    
         case BPT_CODE:    
         {    
            // AddRef the IDebugCodeContext2 of the BP_RESOLUTION_CODE structure.    
            bpResDest.bpResLocation.bpResLocation.bpresCode.pCodeContext->AddRef();    
            break;    
         }    
         case BPT_DATA:    
         {    
            // Copy the bstrDataExpr, bstrFunc, and bstrImage of the  
            // BP_RESOLUTION_DATA structure.    
            bpResDest.bpResLocation.bpResLocation.bpresData.bstrDataExpr =  
               SysAllocString(bpResSrc.bpResLocation.bpResLocation.bpresData.bstrDataExpr);    
            bpResDest.bpResLocation.bpResLocation.bpresData.bstrFunc =  
               SysAllocString(bpResSrc.bpResLocation.bpResLocation.bpresData.bstrFunc);    
            bpResSrc.bpResLocation.bpResLocation.bpresData.bstrImage =  
               SysAllocString(bpResSrc.bpResLocation.bpResLocation.bpresData.bstrImage);    
            break;    
         }    
         default:    
         {    
            assert(FALSE);    
            // Clear the BPRESI_BPRESLOCATION flag in the BPRESI_FIELDS  
            // of the destination BP_RESOLUTION_INFO.    
            ClearFlag(bpResDest.dwFields, BPRESI_BPRESLOCATION);    
            break;    
         }    
      }    
   }    
   // AddRef the IDebugProgram2 if the BPRESI_PROGRAM flag is set in BPRESI_FIELDS.  
   if (IsFlagSet(bpResDest.dwFields, BPRESI_PROGRAM))    
   {    
      bpResDest.pProgram->AddRef();    
   }    
   // AddRef the IDebugThread2 if the BPRESI_THREAD flag is set in BPRESI_FIELDS.  
   if (IsFlagSet(bpResDest.dwFields, BPRESI_THREAD))    
   {    
      bpResDest.pThread->AddRef();    
   }    
  
   return hr;    
}    
```  
  
## 참고 항목  
 [IDebugBreakpointResolution2](../../../extensibility/debugger/reference/idebugbreakpointresolution2.md)   
 [BPRESI\_FIELDS](../../../extensibility/debugger/reference/bpresi-fields.md)   
 [BP\_RESOLUTION\_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md)