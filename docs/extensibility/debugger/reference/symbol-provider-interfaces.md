---
title: "기호 공급자 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "기호 처리기 인터페이스"
  - "기호 처리기, 인터페이스"
  - "기호 처리기, 변수를 평가 합니다."
ms.assetid: 4201f10e-c9f7-4b38-bb45-40fe0082d5bf
caps.latest.revision: 14
caps.handback.revision: 14
ms.author: "gregvanl"
manager: "ghogen"
---
# 기호 공급자 인터페이스
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

다음 기호 처리 인터페이스의 수를 [!INCLUDE[vsipsdk](../../../extensibility/includes/vsipsdk_md.md)].  
  
## 토론  
 이러한 인터페이스는 사용 중단 모드에서 호출 스택에서 변수를 계산 합니다.  공용 언어 런타임에서 기호 공급자만에 대 한 \(SP\) 구현 합니다.  
  
|Interface|관계형 데이터베이스|설명|  
|---------------|----------------|--------|  
|[IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)|SP|항목의 주소를 나타냅니다.|  
|[IDebugAddress2](../../../extensibility/debugger/reference/idebugaddress2.md)|SP|프로세스 ID에 액세스를 제공 하는 항목의 주소를 나타내는|  
|[IDebugArrayField](../../../extensibility/debugger/reference/idebugarrayfield.md)|SP|배열 심볼 또는 배열 형식을 나타냅니다.|  
|[IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)|SP|기호가 클래스 또는 클래스 형식을 나타냅니다.|  
|[IDebugComPlusSymbolProvider](../../../extensibility/debugger/reference/idebugcomplussymbolprovider.md)|SP|COM \+ 기호 공급자를 관리 되는 코드에만 적용 되는 메서드를 나타냅니다.|  
|[IDebugComPlusSymbolProvider2](../../../extensibility/debugger/reference/idebugcomplussymbolprovider2.md)|SP|COM \+ 기호 공급자 관리 되는 코드에만 적용 되는 메서드를 나타냅니다 및 확장 하는  **IDebugComPlusSymbolProvider**.|  
|[IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)|SP|기호나 기타 기호 또는 형식에 대 한 컨테이너 형식을 나타냅니다.|  
|[IDebugCustomAttribute](../../../extensibility/debugger/reference/idebugcustomattribute.md)|SP|기호에 연결할 수 있는 사용자 지정 특성을 나타냅니다.|  
|[IDebugCustomAttributeQuery](../../../extensibility/debugger/reference/idebugcustomattributequery.md)|SP|메서드 또는 형식의 사용자 지정 특성에 대 한 쿼리를 나타냅니다.|  
|[IDebugCustomAttributeQuery2](../../../extensibility/debugger/reference/idebugcustomattributequery2.md)|SP|사용자 지정 특성에 액세스 하는 기호를 제공합니다.|  
|[IDebugDynamicField](../../../extensibility/debugger/reference/idebugdynamicfield.md)|SP|런타임에 결정할 수 있는 형식에 대 한 기본 인터페이스입니다.|  
|[IDebugDynamicFieldCOMPlus](../../../extensibility/debugger/reference/idebugdynamicfieldcomplus.md)|SP|동적 필드를 나타내는 [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md) 개체입니다.|  
|[IDebugEnumField](../../../extensibility/debugger/reference/idebugenumfield.md)|SP|열거형 형식을 나타냅니다.|  
|[IDebugExtendedField](../../../extensibility/debugger/reference/idebugextendedfield.md)|Sp|관리 되는 코드 제네릭을 지원 하기 위해 사용할 수 있는 필드의 종류를 확장 합니다.|  
|[IDebugField](../../../extensibility/debugger/reference/idebugfield.md)|SP|모든 필드에 대 한 기본 클래스입니다. 기호 또는 형식에 대 한 설명을 나타냅니다.|  
|[IDebugGenericFieldDefinition](../../../extensibility/debugger/reference/idebuggenericfielddefinition.md)|SP|관리 되는 코드가 제네릭 형식에 대 한 필드의 정의 나타냅니다.|  
|[IDebugGenericFieldInstance](../../../extensibility/debugger/reference/idebuggenericfieldinstance.md)|SP|관리 되는 코드가 제네릭 형식에 대 한 필드의 인스턴스를 나타냅니다.|  
|[IDebugGenericParamField](../../../extensibility/debugger/reference/idebuggenericparamfield.md)|SP|관리 되는 코드가 제네릭 형식에 대 한 매개 변수를 나타냅니다.|  
|[IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)|SP|메서드를 나타냅니다.|  
|[IDebugModOpt](../../../extensibility/debugger/reference/idebugmodopt.md)|SP|디버그 선택적 한정자를 나타냅니다.|  
|[IDebugPointerField](../../../extensibility/debugger/reference/idebugpointerfield.md)|SP|에 대 한 포인터를 나타냅니다.|  
|[IDebugPrimitiveTypeField](../../../extensibility/debugger/reference/idebugprimitivetypefield.md)|SP|기본 형식의 열거형 값을 나타내는 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 인터페이스입니다.|  
|[IDebugPropertyField](../../../extensibility/debugger/reference/idebugpropertyfield.md)|SP|설정 또는 가져오기 수 하는 관리 되는 코드 클래스의 속성을 나타냅니다.|  
|[IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)|SP|기호 및 형식을 제공 하는 기호 공급자를 나타냅니다.|  
|[IDebugSymbolProviderDirect](../../../extensibility/debugger/reference/idebugsymbolproviderdirect.md)|SP|메타 데이터 및 주요 기호 인터페이스에 기호 공급자를와 직접 연결을 나타냅니다.|  
|[IDebugTypeFieldBuilder](../../../extensibility/debugger/reference/idebugtypefieldbuilder.md)|SP|형식을 나타내는 필드를 만들 수 있는 기능을 나타냅니다.|  
|[IDebugTypeFieldBuilder2](../../../extensibility/debugger/reference/idebugtypefieldbuilder2.md)|SP|확장 되는  **IDebugTypeFieldBuilder** 배열 형식을 만들 수 있습니다.|  
|[IEnumDebugAddresses](../../../extensibility/debugger/reference/ienumdebugaddresses.md)|SP|[IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) 개체의 컬렉션을 나타냅니다.|  
|[IEnumDebugCustomAttributes](../../../extensibility/debugger/reference/ienumdebugcustomattributes.md)|SP|[IDebugCustomAttribute](../../../extensibility/debugger/reference/idebugcustomattribute.md) 개체의 컬렉션을 나타냅니다.|  
|[IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)|SP|[IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 개체의 컬렉션을 나타냅니다.|  
  
## 참고 항목  
 [API 참조](../../../extensibility/debugger/reference/api-reference-visual-studio-debugging.md)