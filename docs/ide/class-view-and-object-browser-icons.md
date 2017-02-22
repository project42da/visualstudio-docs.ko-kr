---
title: "클래스 뷰 및 개체 브라우저 아이콘 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "아이콘, 개체 브라우저"
  - "신호 아이콘"
  - "클래스 뷰 도구, 기호"
  - "그래픽 기호"
  - "IntelliSense, 아이콘"
  - "아이콘, IntelliSense"
  - "기호, 개체 브라우저 아이콘"
  - "개체 브라우저, 클래스 뷰의 아이콘"
ms.assetid: 58cc3f44-c296-4a88-a008-09d28598d9c0
caps.latest.revision: 20
caps.handback.revision: 20
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# 클래스 뷰 및 개체 브라우저 아이콘
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

**클래스 뷰**와 **개체 브라우저**에는 네임스페이스, 클래스, 함수 및 변수와 같은 코드 엔터티를 나타내는 아이콘이 표시됩니다.  다음 표에서는 이러한 아이콘을 보여 주고 각각에 대해 설명합니다.  
  
|아이콘|설명|아이콘|설명|  
|---------|--------|---------|--------|  
|![네임스페이스 기호](../ide/media/vxnamespace_icon.gif "vxNamespace\_Icon")|Namespace|![선언 기호](../ide/media/vxmethod_icon.png "vxMethod\_Icon")|메서드 또는 함수|  
|![클래스 아이콘](../ide/media/vxclass_icon.png "vxClass\_Icon")|클래스|![연산자 기호](../ide/media/vxoperator_icon.png "vxOperator\_Icon")|Operator|  
|![롤리팝 인터페이스 기호](../ide/media/vxinterface_icon.png "vxInterface\_Icon")|Interface|![속성 기호](../ide/media/vxproperty_icon.png "vxProperty\_Icon")|Property|  
|![구조체 기호](../ide/media/vxstruct_icon.png "vxStruct\_Icon")|구조체|![필드 아이콘](../ide/media/vxfield_icon.png "vxField\_Icon")|필드 또는 변수|  
|![공용 구조체 기호](../ide/media/vxunion_icon.png "vxUnion\_Icon")|공용 구조체|![이벤트 기호](../ide/media/vxevent_icon.png "vxEvent\_Icon")|Event|  
|![열거 기호](../ide/media/vxenum_icon.png "vxEnum\_Icon")|Enum|![상수 아이콘](../ide/media/vxconstant_icon.png "vxConstant\_Icon")|상수|  
|![형식 정의 기호](../ide/media/vxtypedef_icon.png "vxTypeDef\_Icon")|TypeDef|![항목 열거 기호](../ide/media/vxenumitem_icon.png "vxEnumItem\_Icon")|열거형 항목|  
|![Visual Studio 모듈 기호](../ide/media/vxmodule_icon.gif "vxModule\_Icon")|모듈|![맵 항목 기호](../ide/media/vxmapitem_icon.png "vxMapItem\_Icon")|맵 항목|  
|![확장 메서드 기호](../ide/media/extensionmethod.png "ExtensionMethod")|확장 메서드|![선언 기호](../ide/media/vxmethod_icon.png "vxMethod\_Icon")|외부 선언|  
|![대리자 기호](../ide/media/vxdelegate_icon.png "vxDelegate\_Icon")|대리자|![클래스 뷰 및 개체 브라우저의 오류 아이콘](../ide/media/erroricon.png "ErrorIcon")|오류|  
|![예외 기호](../ide/media/vxexception_icon.png "vxException\_Icon")|Exception|![템플릿 기호](../ide/media/vxtemplate_icon.png "vxTemplate\_Icon")|템플릿|  
|![맵 기호](../ide/media/vxmap_icon.png "vxMap\_Icon")|맵|![오류 느낌표 기호](../ide/media/vxerror_icon.png "vxError\_Icon")|알 수 없음|  
|![형식 전달 기호](../ide/media/ob_type_forward.png "ob\_type\_forward")|형식 전달|||  
  
## 신호 아이콘  
 다음 신호 아이콘은 앞의 모든 아이콘에 적용되고 아이콘의 액세스 가능성을 나타냅니다.  
  
> [!NOTE]
>  프로젝트가 소스 제어 데이터베이스에 포함되어 있는 경우 체크 인 또는 체크 아웃 같이 소스 제어 상태를 나타내는 추가 신호 아이콘이 표시될 수 있습니다.  
  
|아이콘|설명|  
|---------|--------|  
|\<신호 아이콘 없음\>|Public.  이 구성 요소 내의 모든 곳과 이 구성 요소를 참조하는 모든 구성 요소에서 액세스할 수 있습니다.|  
|![신호 Protected 기호](../ide/media/vxsignal_icon_key.png "vxSignal\_Icon\_Key")|Protected.  포함하는 클래스나 형식 또는 포함하는 클래스나 형식에서 파생된 클래스나 형식에서 액세스할 수 있습니다.|  
|![신호 Private 기호](../ide/media/vxsignal_icon_lock.png "vxSignal\_Icon\_Lock")|Private.  포함하는 클래스나 형식에서만 액세스할 수 있습니다.|  
|![신호 Sealed 기호](../ide/media/vxsignal_icon_envelope.png "vxSignal\_Icon\_Envelope")|봉인.|  
|![신호 Friend&#47;내부 기호](../ide/media/vxsignal_icon_diamond.png "vxSignal\_Icon\_Diamond")|친구\/내부입니다.  프로젝트에서만 액세스할 수 있습니다.|  
|![신호 아이콘 화살표](../ide/media/vxsignal_icon_arrow.gif "vxSignal\_Icon\_Arrow")|Shortcut.  개체에 대한 바로 가기입니다.|  
  
## 참고 항목  
 [코드 구조 보기](../ide/viewing-the-structure-of-code.md)