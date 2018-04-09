---
title: 클래스 뷰 및 개체 브라우저 아이콘 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- icons, in Object Browser
- signal icons
- Class View tool, symbols
- graphic symbols
- IntelliSense, icons
- icons, IntelliSense
- symbols, Object Browser icons
- Object Browser, icons in Class View
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: f0a4371ae086e158f3fd7025e9867ffb99c92090
ms.sourcegitcommit: 29ef88fc7d1511f05e32e9c6e7433e184514330d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/28/2018
---
# <a name="class-view-and-object-browser-icons"></a>클래스 뷰 및 개체 브라우저 아이콘

**클래스 뷰** 및 **개체 브라우저**는 코드 엔터티(예: 네임스페이스, 클래스, 함수 및 변수)를 나타내는 아이콘을 표시합니다. 다음 표에서는 아이콘에 대해 설명합니다.

|아이콘|설명|아이콘|설명|
|----------|-----------------|----------|-----------------|
|![네임스페이스 기호](../ide/media/vxnamespace_icon.gif "vxNamespace_Icon")|네임스페이스|![선언 기호](../ide/media/vxmethod_icon.gif "vxMethod_Icon")|메서드 또는 함수|
|![클래스 아이콘](../ide/media/vxclass_icon.gif "vxClass_Icon")|클래스|![연산자 기호](../ide/media/vxoperator_icon.gif "vxOperator_Icon")|연산자|  
|![롤리팝 인터페이스 기호](../ide/media/vxinterface_icon.gif "vxInterface_Icon")|인터페이스|![속성 기호](../ide/media/vxproperty_icon.gif "vxProperty_Icon")|속성|
|![구조체 기호](../ide/media/vxstruct_icon.gif "vxStruct_Icon")|구조체|![필드 아이콘](../ide/media/vxfield_icon.gif "vxField_Icon")|필드 또는 변수|  
|![공용 구조체 기호](../ide/media/vxunion_icon.gif "vxUnion_Icon")|공용 구조체|![이벤트 기호](../ide/media/vxevent_icon.gif "vxEvent_Icon")|이벤트(event)|  
|![열거형 기호](../ide/media/vxenum_icon.gif "vxEnum_Icon")|Enum|![상수 아이콘](../ide/media/vxconstant_icon.gif "vxConstant_Icon")|상수|  
|![형식 정의 기호](../ide/media/vxtypedef_icon.gif "vxTypeDef_Icon")|TypeDef|![항목 열거 기호](../ide/media/vxenumitem_icon.gif "vxEnumItem_Icon")|항목 열거|  
|![Visual Studio 모듈 기호](../ide/media/vxmodule_icon.gif "vxModule_Icon")|Module|![맵 항목 기호](../ide/media/vxmapitem_icon.gif "vxMapItem_Icon")|맵 항목|  
|![확장명 메서드 기호](../ide/media/extensionmethod.gif "ExtensionMethod")|확장명 메서드|![선언 기호](../ide/media/vxmethod_icon.gif "vxMethod_Icon")|외부 선언|  
|![대리자 기호](../ide/media/vxdelegate_icon.gif "vxDelegate_Icon")|대리자|![클래스 뷰 및 개체 브라우저의 오류 아이콘](../ide/media/erroricon.gif "ErrorIcon")|Error|  
|![예외 기호](../ide/media/vxexception_icon.gif "vxException_Icon")|예외|![템플릿 기호](../ide/media/vxtemplate_icon.gif "vxTemplate_Icon")|템플릿|  
|![맵 기호](../ide/media/vxmap_icon.gif "vxMap_Icon")|맵|![오류 느낌표 기호](../ide/media/vxerror_icon.gif "vxError_Icon")|알 수 없음|  
|![형식 전달 기호](../ide/media/ob_type_forward.gif "ob_type_forward")|형식 전달|||  

## <a name="signal-icons"></a>신호 아이콘

다음 신호 아이콘은 이전의 모든 아이콘에 적용되며 액세스 가능성을 나타냅니다.

|아이콘|설명|
|----------|-----------------|  
|\<신호 없음 아이콘>|공개. 이 구성 요소 및 참조하는 구성 요소의 모든 곳에서 액세스할 수 있습니다.|  
|![신호 보호됨 기호](../ide/media/vxsignal_icon_key.gif "vxSignal_Icon_Key")|보호됨. 포함하는 클래스 또는 형식이나, 여기에서 파생된 클래스 또는 형식에서 액세스할 수 있습니다.|  
|![신호 비공개 기호](../ide/media/vxsignal_icon_lock.gif "vxSignal_Icon_Lock")|비공개. 포함하는 클래스 또는 형식에서만 액세스할 수 있습니다.|  
|![신호 Sealed 기호](../ide/media/vxsignal_icon_envelope.gif "vxSignal_Icon_Envelope")|Sealed.|  
|![신호 Friend&#47;내부 기호](../ide/media/vxsignal_icon_diamond.gif "vxSignal_Icon_Diamond")|Friend/내부. 프로젝트에서만 액세스할 수 있습니다.|  
|![신호 아이콘 화살표](../ide/media/vxsignal_icon_arrow.gif "vxSignal_Icon_Arrow")|바로 가기. 개체에 대한 바로 가기.|

> [!NOTE]
> 프로젝트가 소스 제어 데이터베이스에 포함되어 있는 경우, 추가 신호 아이콘이 표시되어 체크 인 또는 체크 아웃과 같은 소스 제어 상태를 나타낼 수 있습니다.

## <a name="see-also"></a>참고 항목

[코드 구조 보기](../ide/viewing-the-structure-of-code.md)