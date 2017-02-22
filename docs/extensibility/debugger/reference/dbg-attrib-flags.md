---
title: "DBG_ATTRIB_FLAGS | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "DBG_ATTRIB_FLAGS"
helpviewer_keywords: 
  - "DBGPROP_ATTRIB_FLAGS 열거형"
ms.assetid: 2f13e601-dadc-476e-a8ec-01c4515082e7
caps.latest.revision: 17
caps.handback.revision: 17
ms.author: "gregvanl"
manager: "ghogen"
---
# DBG_ATTRIB_FLAGS
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

다양 한 특성에 설명 된 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) 또는 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) 인터페이스입니다.  멤버는 [DEBUG\_PROPERTY\_INFO](../../../extensibility/debugger/reference/debug-property-info.md) 구조입니다.  
  
## 구문  
  
```cpp#  
#define DBG_ATTRIB_NONE                 0x0000000000000000,  
#define DBG_ATTRIB_ALL                  0x00000000ffffffff,  
  
// Attributes about the object itself  
  
#define DBG_ATTRIB_OBJ_IS_EXPANDABLE    0x0000000000000001,  
#define DBG_ATTRIB_OBJ_HAS_ID           0x0000000000000002,  
#define DBG_ATTRIB_OBJ_CAN_HAVE_ID      0x0000000000000004,  
  
// Attributes about the value of the object  
  
#define DBG_ATTRIB_VALUE_READONLY       0x0000000000000010,  
#define DBG_ATTRIB_VALUE_ERROR          0x0000000000000020,  
#define DBG_ATTRIB_VALUE_SIDE_EFFECT    0x0000000000000040,  
#define DBG_ATTRIB_OVERLOADED_CONTAINER 0x0000000000000080,  
#define DBG_ATTRIB_VALUE_BOOLEAN        0x0000000000000100,  
#define DBG_ATTRIB_VALUE_BOOLEAN_TRUE   0x0000000000000200,  
#define DBG_ATTRIB_VALUE_INVALID        0x0000000000000400,  
#define DBG_ATTRIB_VALUE_NAT            0x0000000000000800,  
#define DBG_ATTRIB_VALUE_AUTOEXPANDED   0x0000000000001000,  
#define DBG_ATTRIB_VALUE_TIMEOUT        0x0000000000002000,  
#define DBG_ATTRIB_VALUE_RAW_STRING     0x0000000000004000,  
#define DBG_ATTRIB_VALUE_CUSTOM_VIEWER  0x0000000000008000,  
  
// Attributes about field access types for the object  
  
#define DBG_ATTRIB_ACCESS_NONE          0x0000000000010000,  
#define DBG_ATTRIB_ACCESS_PUBLIC        0x0000000000020000,  
#define DBG_ATTRIB_ACCESS_PRIVATE       0x0000000000040000,  
#define DBG_ATTRIB_ACCESS_PROTECTED     0x0000000000080000,  
#define DBG_ATTRIB_ACCESS_FINAL         0x0000000000100000,  
#define DBG_ATTRIB_ACCESS_ALL           0x00000000001f0000,  
  
// Attributes for the storage types of the object  
  
#define DBG_ATTRIB_STORAGE_NONE         0x0000000001000000,  
#define DBG_ATTRIB_STORAGE_GLOBAL       0x0000000002000000,  
#define DBG_ATTRIB_STORAGE_STATIC       0x0000000004000000,  
#define DBG_ATTRIB_STORAGE_REGISTER     0x0000000008000000,  
#define DBG_ATTRIB_STORAGE_ALL          0x000000000f000000,  
  
// Attributes for the type modifiers on the object  
  
#define DBG_ATTRIB_TYPE_NONE            0x0000000100000000,  
#define DBG_ATTRIB_TYPE_VIRTUAL         0x0000000200000000,  
#define DBG_ATTRIB_TYPE_CONSTANT        0x0000000400000000,  
#define DBG_ATTRIB_TYPE_SYNCHRONIZED    0x0000000800000000,  
#define DBG_ATTRIB_TYPE_VOLATILE        0x0000001000000000,  
#define DBG_ATTRIB_TYPE_ALL             0x0000001f00000000,  
  
// Attributes that describe the type of object  
  
#define DBG_ATTRIB_DATA                 0x0000010000000000,  
#define DBG_ATTRIB_METHOD               0x0000020000000000,  
#define DBG_ATTRIB_PROPERTY             0x0000040000000000,  
#define DBG_ATTRIB_CLASS                0x0000080000000000,  
#define DBG_ATTRIB_BASECLASS            0x0000100000000000,  
#define DBG_ATTRIB_INTERFACE            0x0000200000000000,  
#define DBG_ATTRIB_INNERCLASS           0x0000400000000000,  
#define DBG_ATTRIB_MOSTDERIVED          0x0000800000000000,  
#define DBG_ATTRIB_CHILD_ALL            0x0000ff0000000000,  
  
// Miscellaneous attributes  
  
#define DBG_ATTRIB_MULTI_CUSTOM_VIEWERS 0x0001000000000000  
  
typedef UINT64 DBG_ATTRIB_FLAGS;  
```  
  
```c#  
public const int DBG_ATTRIB_NONE                 = 0x0000000000000000,  
public const int DBG_ATTRIB_ALL                  = 0x00000000ffffffff,  
  
// Attributes about the object itself  
  
public const int DBG_ATTRIB_OBJ_IS_EXPANDABLE    = 0x0000000000000001,  
public const int DBG_ATTRIB_OBJ_HAS_ID           = 0x0000000000000002,  
public const int DBG_ATTRIB_OBJ_CAN_HAVE_ID      = 0x0000000000000004,  
  
// Attributes about the value of the object  
  
public const int DBG_ATTRIB_VALUE_READONLY       = 0x0000000000000010,  
public const int DBG_ATTRIB_VALUE_ERROR          = 0x0000000000000020,  
public const int DBG_ATTRIB_VALUE_SIDE_EFFECT    = 0x0000000000000040,  
public const int DBG_ATTRIB_OVERLOADED_CONTAINER = 0x0000000000000080,  
public const int DBG_ATTRIB_VALUE_BOOLEAN        = 0x0000000000000100,  
public const int DBG_ATTRIB_VALUE_BOOLEAN_TRUE   = 0x0000000000000200,  
public const int DBG_ATTRIB_VALUE_INVALID        = 0x0000000000000400,  
public const int DBG_ATTRIB_VALUE_NAT            = 0x0000000000000800,  
public const int DBG_ATTRIB_VALUE_AUTOEXPANDED   = 0x0000000000001000,  
public const int DBG_ATTRIB_VALUE_TIMEOUT        = 0x0000000000002000,  
public const int DBG_ATTRIB_VALUE_RAW_STRING     = 0x0000000000004000,  
public const int DBG_ATTRIB_VALUE_CUSTOM_VIEWER  = 0x0000000000008000,  
  
// Attributes about field access types for the object  
  
public const int DBG_ATTRIB_ACCESS_NONE          = 0x0000000000010000,  
public const int DBG_ATTRIB_ACCESS_PUBLIC        = 0x0000000000020000,  
public const int DBG_ATTRIB_ACCESS_PRIVATE       = 0x0000000000040000,  
public const int DBG_ATTRIB_ACCESS_PROTECTED     = 0x0000000000080000,  
public const int DBG_ATTRIB_ACCESS_FINAL         = 0x0000000000100000,  
public const int DBG_ATTRIB_ACCESS_ALL           = 0x00000000001f0000,  
  
// Attributes for the storage types of the object  
  
public const int DBG_ATTRIB_STORAGE_NONE         = 0x0000000001000000,  
public const int DBG_ATTRIB_STORAGE_GLOBAL       = 0x0000000002000000,  
public const int DBG_ATTRIB_STORAGE_STATIC       = 0x0000000004000000,  
public const int DBG_ATTRIB_STORAGE_REGISTER     = 0x0000000008000000,  
public const int DBG_ATTRIB_STORAGE_ALL          = 0x000000000f000000,  
  
// Attributes for the type modifiers on the object  
  
public const int DBG_ATTRIB_TYPE_NONE            = 0x0000000100000000,  
public const int DBG_ATTRIB_TYPE_VIRTUAL         = 0x0000000200000000,  
public const int DBG_ATTRIB_TYPE_CONSTANT        = 0x0000000400000000,  
public const int DBG_ATTRIB_TYPE_SYNCHRONIZED    = 0x0000000800000000,  
public const int DBG_ATTRIB_TYPE_VOLATILE        = 0x0000001000000000,  
public const int DBG_ATTRIB_TYPE_ALL             = 0x0000001f00000000,  
  
// Attributes that describe the type of object  
  
public const int DBG_ATTRIB_DATA                 = 0x0000010000000000,  
public const int DBG_ATTRIB_METHOD               = 0x0000020000000000,  
public const int DBG_ATTRIB_PROPERTY             = 0x0000040000000000,  
public const int DBG_ATTRIB_CLASS                = 0x0000080000000000,  
public const int DBG_ATTRIB_BASECLASS            = 0x0000100000000000,  
public const int DBG_ATTRIB_INTERFACE            = 0x0000200000000000,  
public const int DBG_ATTRIB_INNERCLASS           = 0x0000400000000000,  
public const int DBG_ATTRIB_MOSTDERIVED          = 0x0000800000000000,  
public const int DBG_ATTRIB_CHILD_ALL            = 0x0000ff0000000000,  
  
// Miscellaneous attributes  
  
public const int DBG_ATTRIB_MULTI_CUSTOM_VIEWERS = 0x0001000000000000  
```  
  
## Members  
 DBG\_ATTRIB\_NONE  
 특성을 나타냅니다.  
  
 DBG\_ATTRIB\_ALL  
 모든 특성을 나타냅니다.  
  
 DBG\_ATTRIB\_OBJ\_IS\_EXPANDABLE  
 어린이를 참조 했음을 나타냅니다.  
  
 DBG\_ATTRIB\_OBJ\_HAS\_ID  
 이 개체에 대 한 ID 생성 되었음을 나타냅니다.  
  
 DBG\_ATTRIB\_OBJ\_CAN\_HAVE\_ID  
 이 개체를 만들 수 없음을 나타냅니다.  
  
 DBG\_ATTRIB\_VALUE\_READONLY  
 값 읽기 전용임을 나타냅니다.  
  
 DBG\_ATTRIB\_VALUE\_ERROR  
 오류 값입니다.  
  
 DBG\_ATTRIB\_VALUE\_SIDE\_EFFECT  
 평가 부작용 있음을 나타냅니다.  
  
 DBG\_ATTRIB\_OVERLOADED\_CONTAINER  
 이 속성은 컨테이너의 오버 로드입니다.  
  
 DBG\_ATTRIB\_VALUE\_BOOLEAN  
 나타내는 값에 `DEBUG_PROPERTY_INFO::bstrValue` 부울 값입니다.  
  
 DBG\_ATTRIB\_VALUE\_BOOLEAN\_TRUE  
 나타내는 값에 `DEBUG_PROPERTY_INFO::bstrValue` 부울입니다 및 `TRUE`.  
  
 DBG\_ATTRIB\_VALUE\_INVALID  
 나타내는 값에 `DEBUG_PROPERTY_INFO::bstrValue` 유효 하지 않습니다.  
  
 DBG\_ATTRIB\_VALUE\_NAT  
 값 `DEBUG_PROPERTY_INFO::bstrValue` 입니다 "*는 것*은" \(NAT\).  NAT 지연 된 추론 예외를 나타내는 레지스터 플래그 64\-비트 프로세서에 설명 합니다.  
  
 DBG\_ATTRIB\_VALUE\_AUTOEXPANDED  
 나타내는 값에 `DEBUG_PROPERTY_INFO::bstrValue` 가능한 경우 자동 확장 되었습니다.  
  
 DBG\_ATTRIB\_VALUE\_TIMEOUT  
 평가 시간 초과 되었습니다 나타냅니다.  
  
 DBG\_ATTRIB\_VALUE\_RAW\_STRING  
 나타내는 값에 `DEBUG_PROPERTY_INFO::bstrValue` 에서 원시 문자열로 표시 될 수 있습니다.  
  
 DBG\_ATTRIB\_VALUE\_CUSTOM\_VIEWER  
 이 속성에 연결 된 사용자 지정 뷰어를 하나 이상가지고 있음을 나타냅니다.  
  
 DBG\_ATTRIB\_ACCESS\_NONE  
 둘 다가 있는 개체를 나타냅니다 `public`, `private`, 또는 `protected` 액세스를 입력 합니다.  
  
 DBG\_ATTRIB\_ACCESS\_PUBLIC  
 공용 액세스 권한을 가진 개체를 나타냅니다.  
  
 DBG\_ATTRIB\_ACCESS\_PRIVATE  
 Private 액세스 권한을 있는 개체를 나타냅니다.  
  
 DBG\_ATTRIB\_ACCESS\_PROTECTED  
 액세스를 보호 하는 개체를 나타냅니다.  
  
 DBG\_ATTRIB\_ACCESS\_FINAL  
 최종 액세스 된 개체를 나타냅니다.  
  
 DBG\_ATTRIB\_ACCESS\_ALL  
 액세스 특성에서 추출 합니다 마스크 `DBG_ATTRIB_FLAGS`.  
  
 DBG\_ATTRIB\_STORAGE\_NONE  
 지정 된 저장소 형식이 임을 나타냅니다.  
  
 DBG\_ATTRIB\_STORAGE\_GLOBAL  
 전역 저장소를 나타냅니다.  
  
 DBG\_ATTRIB\_STORAGE\_STATIC  
 정적 저장소를 나타냅니다.  
  
 DBG\_ATTRIB\_STORAGE\_REGISTER  
 등록에 대 한 저장소를 나타냅니다.  
  
 DBG\_ATTRIB\_STORAGE\_ALL  
 저장소 속성을 추출 하려면 마스크 `DBG_ATTRIB_FLAGS`.  
  
 DBG\_ATTRIB\_TYPE\_NONE  
 형식 한정자가 있음을 나타냅니다.  
  
 DBG\_ATTRIB\_TYPE\_VIRTUAL  
 개체 유형의 가상입니다.  
  
 DBG\_ATTRIB\_TYPE\_CONSTANT  
 개체의 형식 상수입니다.  
  
 DBG\_ATTRIB\_TYPE\_SYNCHRONIZED  
 동기화 개체의 형식을 나타냅니다.  
  
 DBG\_ATTRIB\_TYPE\_VOLATILE  
 개체의 형식을 일시적입니다.  
  
 DBG\_ATTRIB\_TYPE\_ALL  
 마스크 형식 특성을 추출 하려면 `DBG_ATTRIB_FLAGS`.  
  
 DBG\_ATTRIB\_DATA  
 이 개체는 데이터 필드입니다.  
  
 DBG\_ATTRIB\_METHOD  
 이 개체는 방법입니다.  
  
 DBG\_ATTRIB\_PROPERTY  
 이 개체의 속성입니다.  
  
 DBG\_ATTRIB\_CLASS  
 이 개체의 클래스입니다.  
  
 DBG\_ATTRIB\_BASECLASS  
 이 개체는 기본 클래스입니다.  
  
 DBG\_ATTRIB\_INTERFACE  
 이 개체는 인터페이스입니다.  
  
 DBG\_ATTRIB\_INNERCLASS  
 이 개체는 내부 클래스입니다.  
  
 DBG\_ATTRIB\_MOSTDERIVED  
 이 개체가 나타내는 '*최대 파생*'.  라는 용어 "*가장 많이 파생*"은 개체의 실제 형식이 고 해당 참조 형식을 의미 합니다.  
  
 DBG\_ATTRIB\_CHILD\_ALL  
 마스크를 나타내는 `DBG_ATTRIB_DATA` \- `DBG_ATTRIB_MOSTDERIVED`.  
  
 DBG\_ATTRIB\_MULTI\_CUSTOM\_VIEWERS  
 여러 사용자 지정 뷰어에서 연결 된 개체가 있음을 나타냅니다.  
  
## 설명  
  
> [!NOTE]
>  어셈블리에 C\# 값이이 열거형에서 실제로 정의 되지 않습니다.  대신 소스 파일에 정의 복사 해야 합니다.  
  
 이러한 플래그는 개체의 자식에 대 한 인수로 전달 될 때 필터링에 사용 됩니다 [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md).  값의 비트와 함께 사용할 수 있습니다 `OR`.  
  
 `DBG_ATTRIB_VALUE_CUSTOM_VIEWER` 플래그를 표시 하는 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] 얻을 수는 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md) 에서 인터페이스는 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) 인터페이스와 호출 [GetCustomViewerList](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewerlist.md) 사용자 지정 뷰어에서 목록에 대 한.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)   
 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)   
 [DEBUG\_PROPERTY\_INFO](../../../extensibility/debugger/reference/debug-property-info.md)