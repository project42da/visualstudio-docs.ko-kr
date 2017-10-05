---
title: IDebugProgramPublisher2::PublishProgram | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugProgramPublisher2::PublishProgram
helpviewer_keywords:
- IDebugProgramPublisher2::PublishProgram
ms.assetid: 92ff63f0-e869-4040-b3ae-b2c899e708ff
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: MT
ms.sourcegitcommit: 4a36302d80f4bc397128e3838c9abf858a0b5fe8
ms.openlocfilehash: 3f573f35ed0130eb020ac2e8e19a0391050ec06e
ms.contentlocale: ko-kr
ms.lasthandoff: 09/26/2017

---
# <a name="idebugprogrampublisher2publishprogram"></a>IDebugProgramPublisher2::PublishProgram
이 메서드는 디버그 엔진 (DEs)에 사용할 수 있는 프로그램 및 세션 디버그 관리자를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT PublishProgram(  
   CONST_GUID_ARRAY Engines,  
   LPCOLESTR        szFriendlyName,  
   IUnknown*        pDebuggeeInterface  
);  
```  
  
```csharp  
int PublishProgram(  
   CONST_GUID_ARRAY Engines,  
   string           szFriendlyName,  
   object           pDebuggeeInterface  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `Engines`  
 [in] 배열 des를 시작 하거나이 프로그램에 연결할 수 있는 Guid입니다.  
  
 `szFriendlyName`  
 [in] (메뉴 또는 대화 상자에는 사용자에 게 표시) 프로그램에 대 한 이름입니다.  
  
 `pDebuggeeInterface`  
 [in] `IUnknown` 프로그램에 대 한 인터페이스 (이 값은 고유 하 게 식별 프로그램 쿠키로 사용, "프로그램을 게시"는 동일한이 값은 사용)  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 프로그램을 디버깅을 위해 더 이상 사용할 수 있도록 하려면 호출 [UnpublishProgram](../../../extensibility/debugger/reference/idebugprogrampublisher2-unpublishprogram.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProgramPublisher2](../../../extensibility/debugger/reference/idebugprogrampublisher2.md)   
 [UnpublishProgram](../../../extensibility/debugger/reference/idebugprogrampublisher2-unpublishprogram.md)
