---
title: "Windows 런타임 API를 사용할 때의 고려 사항 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "javascript"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "JavaScript, Windows 런타임 API"
ms.assetid: 2f56d70c-c80d-4876-8e6a-8ae031d31c22
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# Windows 런타임 API를 사용할 때의 고려 사항
JavaScript에서 런타임 Windows API의 거의 모든 요소를 사용할 수 있습니다.  그러나 JavaScript에서 Windows 런타임 요소를 표현하는 방식 중 몇 가지 주의해야 할 점이 있습니다.  
  
> [!IMPORTANT]
>  C\+\+, C\# 또는 Visual Basic에서 Windows 런타임 구성 요소를 만들기와 JavaScript에서 사용하는 방법에 대한 자세한 내용은 [Windows Runtime 구성 요소 만들기](../Topic/Creating%20Windows%20Runtime%20Components.md)을\(를\) 참조하십시오.  
  
## JavaScript에서 Windows 런타임 형식의 특수 표현 사례  
  
-   문자열: 초기화되지 않은 문자열은 Windows 런타임 메서드에 "undefined"라는 문자열로 전달되고 `null`로 설정된 문자열은 "null" 문자열로 전달됩니다. \(`null` 또는 `undefined` 값이 문자열로 강제 변환되는 경우가 해당합니다.\) 문자열을 Windows 런타임 메서드로 전달하기 전에 빈 문자열\(""\)로 초기화해야 합니다.  
  
-   인터페이스: JavaScript에서는 Windows 런타임 인터페이스를 구현할 수 없습니다.  
  
-   배열: Windows 런타임 배열은 크기를 조정할 수 없으므로 JavaScript에서 배열 크기를 조정하는 메서드는 Windows 런타임 배열에서 작동하지 않습니다.  
  
-   배열: JavaScript 배열 값을 Windows 런타임 메서드에 전달하면 배열이 복사됩니다.  Windows 런타임 메서드는 배열 또는 해당 멤버를 수정하여 사용자의 JavaScript 응용 프로그램으로 반환할 수 없습니다.  그러나 복사되지 않는 형식화된 배열은 사용할 수 있습니다\(예: [Int32Array 개체](../javascript/reference/int32array-object.md)\).  
  
-   구조체: JavaScript에서 Windows 런타임 구조체는 개체입니다.  Windows 런타임 구조체를 Windows 런타임 메서드로 전달하려는 경우 `new` 키워드로 구조체를 인스턴스화하지 마십시오.  대신 개체를 만들고 관련된 멤버와 해당 값을 추가합니다.  멤버 이름은 카멜식 대\/소문자: `SomeStruct.firstMember`여야 합니다.  
  
-   개체: JavaScript 개체는 관리되는 코드 개체\(`System.Object`\)와 같지 않습니다.  JavaScript 개체를 `System.Object`가 필요한 Windows 런타임 메서드로 전달할 수 없습니다.  
  
-   개체 ID: 대부분의 경우 Windows 런타임과 JavaScript 사이에서 반복 전달되는 개체는 변경되지 않습니다.  JavaScript 엔진은 알려진 개체의 맵을 유지합니다.  개체가 Windows 런타임 개체에서 반환되면 맵에 해당 개체가 있는지 확인하고 없으면 새 개체를 만듭니다.  Windows 런타임 메서드에서 반환한 인터페이스를 나타내는 개체에 대해서도 동일한 절차를 따릅니다.  예외에는 두 가지 종류가 있습니다.  
  
    -   Windows 런타임 호출에서 반환된 다음 새\(expando\) 속성이 추가된 개체를 다시 Windows 런타임으로 전달하면 새 속성이 유지되지 않습니다.  그러나 JavaScript 응용 프로그램으로 반환할 경우 기존 개체와 비교 확인하므로 반환된 개체에는 expando 속성이 없습니다.  
  
    -   Windows 런타임의 구조체 및 대리자는 이전에 사용된 구조체 또는 대리자와 동일한 것으로 식별할 수 없습니다.  구조체 또는 대리자가 반환될 때마다 새 참조를 가져옵니다.  
  
-   이름 충돌: 여러 Windows 런타임 인터페이스가 동일한 이름의 멤버를 가질 수 있습니다.  단일 JavaScript 개체로 결합되면\(런타임 클래스 또는 인터페이스의 표현이 될 수 있음\) 멤버가 정규화된 이름으로 표현됩니다.  `Class["MemberName"](parameter)` 구문을 사용하여 멤버를 호출할 수 있습니다.  
  
     다음 코드에서는 두 인터페이스에 Draw 메서드가 있고 런타임 클래스가 두 인터페이스를 구현합니다.  
  
    ```cpp#  
    namespace CollisionExample {  
        interface InterfaceA  
        {  
            HRESULT Draw([in] Int32 a);  
        }  
        interface InterfaceB  
        {  
            HRESULT Draw([in] HString a);  
        }  
        runtimeclass ExampleObject {  
          interface InterfaceA  
          interface InterfaceB  
        }  
    }  
    ```  
  
     JavaScript에서 위의 코드를 호출하는 방법은 다음과 같습니다.  
  
    ```javascript  
    var example = new ExampleObject();  
    example["CollisionExample.InterfaceA.draw"](12);  
    example["CollisionExample.InterfaceB.draw"]("hello");  
    ```  
  
-   `Out` 매개 변수: Windows 런타임 메서드에 여러 `out` 매개 변수가 있는 경우, JavaScript에서 해당 메서드는 반환 값으로 JavaScript 개체를 갖고 개체는 `out` 매개 변수에 해당하는 속성을 갖습니다.  예를 들어, C\+\+에서 다음 Windows 런타임 시그니처를 참조하십시오.  
  
    ```cpp#  
    void ExampleMethod(  
      [OutAttribute] char^ first,   
      [OutAttribute] char^ second  
    )  
    ```  
  
     이 시그니처의 JavaScript 버전은 다음과 같습니다.  
  
    ```javascript  
    var returnValue = exampleMethod();  
  
    ```  
  
     이 예제에서 `returnValue`는 `first` 및 `second`의 두 필드를 가진 JavaScript 개체입니다.  
  
-   정적 멤버: Windows 런타임은 정적 멤버 및 인스턴스 멤버를 모두 정의합니다.  JavaScript에서 정적 멤버는 Windows 런타임 클래스 또는 인터페이스와 연결된 개체에 추가됩니다.  
  
    ```javascript  
    // Static method.   
    var accel = Windows.Devices.Sensors.Accelerometer.getDefault();   
    // Instance method.   
    var reading = accel.getCurrentReading();            
    ```  
  
 Windows 런타임 기본 형식의 JavaScript 표현에 대한 자세한 내용은 [Windows 런타임 형식의 JavaScript 표현](../jswinrt/javascript-representation-of-windows-runtime-types.md)을\(를\) 참조하십시오.