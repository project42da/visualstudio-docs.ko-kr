---
title: "공급자 인터페이스 기호 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- interfaces, symbol handler
- symbol handler, interfaces
- symbol handler, evaluating variables
ms.assetid: 4201f10e-c9f7-4b38-bb45-40fe0082d5bf
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 84b8e517efa7c5c4aaeba4bf6e19dc23b0615eda
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="symbol-provider-interfaces"></a>기호 공급자 인터페이스
다음은에 대 한 기호를 처리 인터페이스는 [!INCLUDE[vsipsdk](../../../extensibility/includes/vsipsdk_md.md)]합니다.  
  
## <a name="discussion"></a>토론  
 이러한 인터페이스는 중단 모드에 있는 동안 호출 스택에 있는 변수를 평가 하는 데 사용 됩니다. 공용 언어 런타임 기호 공급자 (SP)에 대해서만 구현 됩니다.  
  
|인터페이스|에 의해 구현|설명|  
|---------------|--------------------|-----------------|  
|[IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)|SP|항목의 주소를 나타냅니다.|  
|[IDebugAddress2](../../../extensibility/debugger/reference/idebugaddress2.md)|SP|프로세스 ID에 대 한 액세스를 제공 하는 항목의 주소를 나타냅니다.|  
|[IDebugArrayField](../../../extensibility/debugger/reference/idebugarrayfield.md)|SP|배열 기호 또는 배열 형식을 나타냅니다.|  
|[IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)|SP|클래스 형식 또는 클래스 기호를 나타냅니다.|  
|[IDebugComPlusSymbolProvider](../../../extensibility/debugger/reference/idebugcomplussymbolprovider.md)|SP|관리 코드에만 적용 되는 메서드와 함께 COM + 기호 공급자를 나타냅니다.|  
|[IDebugComPlusSymbolProvider2](../../../extensibility/debugger/reference/idebugcomplussymbolprovider2.md)|SP|관리 코드에만 적용 되는 메서드와 함께 COM + 기호 공급자를 나타내며 확장는 **IDebugComPlusSymbolProvider**합니다.|  
|[IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)|SP|기호 또는 다른 기호 또는 형식에 대 한 컨테이너 형식을 나타냅니다.|  
|[IDebugCustomAttribute](../../../extensibility/debugger/reference/idebugcustomattribute.md)|SP|기호를 첨부할 수 있는 사용자 지정 특성을 나타냅니다.|  
|[IDebugCustomAttributeQuery](../../../extensibility/debugger/reference/idebugcustomattributequery.md)|SP|메서드 또는 형식에 사용자 지정 특성에 대 한 쿼리를 나타냅니다.|  
|[IDebugCustomAttributeQuery2](../../../extensibility/debugger/reference/idebugcustomattributequery2.md)|SP|기호에 대해 사용자 지정 특성에 대 한 액세스를 제공합니다.|  
|[IDebugDynamicField](../../../extensibility/debugger/reference/idebugdynamicfield.md)|SP|런타임 시 확인할 수 있는 모든 형식에 대 한 기본 인터페이스입니다.|  
|[IDebugDynamicFieldCOMPlus](../../../extensibility/debugger/reference/idebugdynamicfieldcomplus.md)|SP|에 대 한 동적 필드를 나타냅니다는 [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md) 개체입니다.|  
|[IDebugEnumField](../../../extensibility/debugger/reference/idebugenumfield.md)|SP|열거형을 나타냅니다.|  
|[IDebugExtendedField](../../../extensibility/debugger/reference/idebugextendedfield.md)|s p|관리 코드 제네릭을 지원 하기 위해 사용할 수 있는 필드의 형식을 확장 합니다.|  
|[IDebugField](../../../extensibility/debugger/reference/idebugfield.md)|SP|모든 필드에 대 한 기본 클래스 기호 또는 형식에 대 한 설명을 나타냅니다.|  
|[IDebugGenericFieldDefinition](../../../extensibility/debugger/reference/idebuggenericfielddefinition.md)|SP|관리 코드 제네릭 형식에 대 한 필드의 정의 나타냅니다.|  
|[IDebugGenericFieldInstance](../../../extensibility/debugger/reference/idebuggenericfieldinstance.md)|SP|관리 코드 제네릭 형식에 대 한 필드의 인스턴스를 나타냅니다.|  
|[IDebugGenericParamField](../../../extensibility/debugger/reference/idebuggenericparamfield.md)|SP|관리 코드 제네릭 형식에 대 한 매개 변수를 나타냅니다.|  
|[IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)|SP|메서드를 나타냅니다.|  
|[IDebugModOpt](../../../extensibility/debugger/reference/idebugmodopt.md)|SP|디버그 선택적 한정자를 나타냅니다.|  
|[IDebugPointerField](../../../extensibility/debugger/reference/idebugpointerfield.md)|SP|포인터를 나타냅니다.|  
|[IDebugPrimitiveTypeField](../../../extensibility/debugger/reference/idebugprimitivetypefield.md)|SP|기본 형식 열거형 값을 나타내는 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 인터페이스입니다.|  
|[IDebugPropertyField](../../../extensibility/debugger/reference/idebugpropertyfield.md)|SP|Get 또는 설정할 수 있는 관리 코드 클래스의 속성을 나타냅니다.|  
|[IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)|SP|기호 및 형식을 제공 하는 기호 공급자를 나타냅니다.|  
|[IDebugSymbolProviderDirect](../../../extensibility/debugger/reference/idebugsymbolproviderdirect.md)|SP|메타 데이터와 핵심 기호 인터페이스에 직접 액세스할 수 있는 기호 공급자를 나타냅니다.|  
|[IDebugTypeFieldBuilder](../../../extensibility/debugger/reference/idebugtypefieldbuilder.md)|SP|형식을 나타내는 필드를 만들 수 있는 기능을 나타냅니다.|  
|[IDebugTypeFieldBuilder2](../../../extensibility/debugger/reference/idebugtypefieldbuilder2.md)|SP|확장 된 **IDebugTypeFieldBuilder** 배열 형식을 만들 수 있습니다.|  
|[IEnumDebugAddresses](../../../extensibility/debugger/reference/ienumdebugaddresses.md)|SP|컬렉션을 나타냅니다 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) 개체입니다.|  
|[IEnumDebugCustomAttributes](../../../extensibility/debugger/reference/ienumdebugcustomattributes.md)|SP|컬렉션을 나타냅니다 [IDebugCustomAttribute](../../../extensibility/debugger/reference/idebugcustomattribute.md) 개체입니다.|  
|[IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)|SP|컬렉션을 나타냅니다 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 개체입니다.|  
  
## <a name="see-also"></a>참고 항목  
 [API 참조](../../../extensibility/debugger/reference/api-reference-visual-studio-debugging.md)