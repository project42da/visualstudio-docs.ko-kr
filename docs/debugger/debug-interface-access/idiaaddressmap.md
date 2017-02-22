---
title: "IDiaAddressMap | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDiaAddressMap 인터페이스"
ms.assetid: e6467529-508c-4328-85d7-89444ae4d1c1
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# IDiaAddressMap
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

DIA SDK 가상 및 상대 가상 주소 디버그 개체를 계산 하는 방법을 제어할을 수 있습니다.  
  
## 구문  
  
```  
IDiaAddressMap : IUnknown  
```  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDiaAddressMap`.  
  
|메서드|설명|  
|---------|--------|  
|[IDiaAddressMap::get\_addressMapEnabled](../../debugger/debug-interface-access/idiaaddressmap-get-addressmapenabled.md)|주소 맵 특정 세션에 대해 설정 되었는지 여부를 나타냅니다.|  
|[IDiaAddressMap::put\_addressMapEnabled](../../debugger/debug-interface-access/idiaaddressmap-put-addressmapenabled.md)|주소 맵 기호 주소를 변환에 사용할 것인지 여부를 지정 합니다.|  
|[IDiaAddressMap::get\_relativeVirtualAddressEnabled](../../debugger/debug-interface-access/idiaaddressmap-get-relativevirtualaddressenabled.md)|계산 및 사용 하는 상대 가상 주소가 사용 여부를 나타냅니다.|  
|[IDiaAddressMap::put\_relativeVirtualAddressEnabled](../../debugger/debug-interface-access/idiaaddressmap-put-relativevirtualaddressenabled.md)|계산의 상대 가상 주소를 사용할지 여부는 클라이언트를 허용 합니다.|  
|[IDiaAddressMap::get\_imageAlign](../../debugger/debug-interface-access/idiaaddressmap-get-imagealign.md)|현재 이미지 맞춤을 검색합니다.|  
|[IDiaAddressMap::put\_imageAlign](../../debugger/debug-interface-access/idiaaddressmap-put-imagealign.md)|이미지 맞춤을 설정 합니다.|  
|[IDiaAddressMap::set\_imageHeaders](../../debugger/debug-interface-access/idiaaddressmap-set-imageheaders.md)|집합 번역의 상대 가상 주소를 사용 하려면 머리글 이미지.|  
|[IDiaAddressMap::set\_addressMap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md)|이미지가 레이아웃 변환을 지원 하기 위해 주소 맵을 제공 합니다.|  
  
## 설명  
 이 인터페이스에서 제공 하는 컨트롤에 두 가지 입력 데이터 캡슐화 됩니다: 머리글 이미지 및 지도 해결 합니다.  대부분의 클라이언트가 사용 하는 [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) 이미지 및 방법 일반적으로 모든 필요한 헤더 및 맵 데이터 자체의 검색 수 있습니다에 대 한 적절 한 디버그 정보를 찾는 방법입니다.  그러나 일부 클라이언트 특수 처리와 데이터 검색을 구현 합니다.  클라이언트의 메서드를 사용 하는 `IDiaAddressMap` DIA SDK를 검색 결과 함께 제공 하는 인터페이스입니다.  
  
## 호출자에 대 한 참고 사항  
 이 인터페이스는 DIA 세션 개체를 사용할 수 있습니다.  클라이언트 호출의 `QueryInterface` DIA 세션 개체 인터페이스에, 일반적으로 메서드 [IDiaSession](../../debugger/debug-interface-access/idiasession.md), 검색 하는 `IDiaAddressMap` 인터페이스입니다.  
  
## 요구 사항  
 헤더: Dia2.h  
  
 라이브러리: diaguids.lib  
  
 DLL: msdia80.dll  
  
## 참고 항목  
 [인터페이스\(디버그 인터페이스 액세스 SDK\)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)   
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)