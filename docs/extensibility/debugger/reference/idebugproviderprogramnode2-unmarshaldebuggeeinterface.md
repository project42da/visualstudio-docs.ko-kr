---
title: IDebugProviderProgramNode2::UnmarshalDebuggeeInterface | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugProviderProgramNode2::UnmarshalDebuggeeInterface
helpviewer_keywords:
- IDebugProviderProgramNode2::UnmarshalDebuggeeInterface
ms.assetid: 2e4653c5-10f1-493c-9973-f31d266c5d48
caps.latest.revision: 10
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: c0f09d5b5fb1d420eef6b91ea596adbcab665ded
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/10/2018
---
# <a name="idebugproviderprogramnode2unmarshaldebuggeeinterface"></a>IDebugProviderProgramNode2::UnmarshalDebuggeeInterface
프로세스 경계에 걸쳐 지정된 된 인터페이스를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT UnmarshalDebuggeeInterface(  
   REFIID riid,  
   void** ppvObject  
);  
```  
  
```csharp  
int UnmarshalDebuggeeInterface(  
   ref Guid   riid,  
   out IntPtr ppvObject  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `riid`  
 [in] 가져올 인터페이스의 GUID입니다.  
  
 `ppvObject`  
 [out] 원하는 인터페이스를 구현 하는 개체를 반환 합니다. [C + +] 원하는 인터페이스 유형으로 직접 캐스팅 될 수 있습니다. 사용 [C#]는 <xref:System.Runtime.InteropServices.Marshal.GetObjectForIUnknown%2A> 메서드 원하는 인터페이스를 가져올 수 있습니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 디버그 엔진에서 실행 중인 경우이 메서드는는 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] 프로세스 공간 있고 디버깅 중인 프로그램 자체 프로세스 공간에서 실행 되 고 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProviderProgramNode2](../../../extensibility/debugger/reference/idebugproviderprogramnode2.md)