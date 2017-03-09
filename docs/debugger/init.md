---
title: "Init | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c55ddec8-9101-4673-979b-4109caca9146
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# Init
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

적극적으로 캡처하고 그래픽 정보 그래픽 로그 파일에 기록하기 위해 그래픽 진단 응용 프로그램의 구성 요소를 준비 합니다.  
  
## 구문  
  
```cpp  
void Init(  
  std::function<void (int len, wchar_t * pszBuffer)> vsgLogGetter  
);  
```  
  
#### 매개 변수  
 `vsgLogGetter`  
 호출 가능한 엔터티—예를 들어 함수, 함수 포인터, 람다, 또는 함수 개체 같이 `wchar_t` 및 해당 버퍼의 포인터로 이루어진 버퍼의 길이를 매개변수로 취하고 `void` 를 반환하는 엔터티 입니다.  호출되면 호출 가능 엔터티는 그래픽 정보를 기록하는 파일의 이름을 결정하고, 반환 하기 전에 이 정보들을 지정된 버퍼에 씁니다.  
  
## 설명  
 `Init` 함수는 `VsgDbg` 클래스의 인스턴스가 해당 생성자의 `bDefaultInit` 매개 변수를 `true` 로 지정하여 생성될 때 자동으로 호출됩니다. 그렇지 않으면 `Init` 은 그래픽 정보를 적극적으로 캡처 및 기록 하기 전에 명시적으로 호출되야 합니다.  
  
 `UnInit` 를 호출하여 액티브 그래픽 로그 파일을 종료하고 닫을 수 있고, 그런 다음 `Init` 을 다시 호출하여 더 많은 그래픽 정보를 새 그래픽 로그 파일에 기록 및 캡처 할 수 있습니다.  이것을 동일한 `VsgDbg` 인스턴스를 사용하여 여러 독립 그래픽 로그 파일을 만들고 싶은 만큼 여러번 반복할 수 있습니다.  
  
## 참고 항목  
 [UnInit](../debugger/init.md)