---
title: "Windows 런타임 API 사용 시 고려 사항 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- javascript
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- JavaScript, Windows Runtime API
ms.assetid: 2f56d70c-c80d-4876-8e6a-8ae031d31c22
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 693b3dac9def5533417638c3ec1c0de8db1d5fe3
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="considerations-when-using-the-windows-runtime-api"></a>Windows 런타임 API 사용 시 고려 사항
Windows 런타임 API의 거의 모든 요소를 JavaScript에서 사용할 수 있습니다. 그러나 Windows 런타임 요소의 JavaScript 표현에는 사용자가 유의해야 하는 몇 가지 요소가 있습니다.  
  
> [!IMPORTANT]
>  C++, C# 또는 Visual Basic으로 Windows 런타임 구성 요소를 만들고 JavaScript에서 사용하는 데 대한 자세한 내용은 [C++로 Windows 런타임 구성 요소 만들기](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)와 [C# 및 Visual Basic으로 Windows 런타임 구성 요소 만들기](/windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic)를 참조하세요.  
  
## <a name="special-cases-in-the-javascript-representation-of-windows-runtime-types"></a>Windows 런타임 형식 JavaScript 표현의 특수 사례  
  
-   문자열: 초기화되지 않은 문자열은 “undefined” 문자열로 Windows 런타임 메서드에 전달되고 `null`로 설정된 문자열은 “null” 문자열로 전달됩니다. (이 동작은 `null` 또는 `undefined` 값을 문자열로 강제 변환할 때마다 적용됩니다.) Windows 런타임 메서드에 문자열을 전달하기 전에 비어 있는 문자열(“”)로 초기화해야 합니다.  
  
-   인터페이스: JavaScript에서 Windows 런타임 인터페이스를 구현할 수 없습니다.  
  
-   배열: Windows 런타임 배열의 크기를 조정할 수 없으므로, JavaScript에서 배열의 크기를 조정하는 메서드는 Windows 런타임 배열에서 적용할 수 없습니다.  
  
-   배열: Windows 런타임 메서드에 JavaScript 배열 값을 전달하는 경우 배열이 복사됩니다. Windows 런타임 메서드를 통해 배열 또는 해당 멤버를 수정하고 JavaScript 앱에 반환할 수 없습니다. 그러나 복사되지 않는 형식화된 배열(예: [Int32Array 개체](../javascript/reference/int32array-object.md))을 사용할 수 있습니다.  
  
-   구조체: Windows 런타임 구조는 JavaScript의 개체입니다. Windows 런타임 구조체를 Windows 런타임 메서드에 전달하려는 경우 `new` 키워드로 구조를 인스턴스화하지 마세요. 대신 개체를 만들고 관련 멤버 및 해당 값을 추가합니다. 멤버의 이름이 카멜 대/소문자여야 합니다. `SomeStruct.firstMember`.  
  
-   개체: JavaScript 개체가 관리 코드 개체와 다릅니다(`System.Object`). `System.Object`가 필요한 Windows 런타임 메서드에 JavaScript 개체를 전달할 수 없습니다.  
  
-   개체 ID: Windows 런타임과 JavaScript 간에 서로 전달하는 개체는 대부분의 경우 변경되지 않습니다. JavaScript 엔진에서 알려진 개체의 맵을 유지 관리합니다. Windows 런타임에서 개체를 반환하면 맵과 비교하여 일치하는지 확인하고, 개체가 없으면 새 개체를 만듭니다. Windows 런타임 메서드에서 반환한 인터페이스를 나타내는 개체에 대해 동일한 절차가 다음으로 수행됩니다. 다음과 같은 두 가지 종류의 예외가 있습니다.  
  
    -   Windows 런타임 호출에서 반환된 다음 새(expando) 속성이 추가된 개체는 Windows 런타임에 다시 전달할 때 새 속성을 유지하지 않습니다. 그러나 JavaScript 앱에 반환될 때는 기존 개체와 일치되므로 반환된 개체에 expando 속성이 있습니다.  
  
    -   Windows 런타임의 구조와 대리자는 이전에 사용된 구조 또는 대리자와 동일한 것으로 확인할 수 없습니다. 구조나 대리자를 반환할 때마다 새 참조를 얻습니다.  
  
-   이름 충돌: 여러 Windows 런타임 인터페이스에 이름이 같은 멤버가 있을 수 있습니다. 단일 JavaScript 개체(런타임 클래스 또는 인터페이스 표시일 수 있음)에 결합되면 정규화된 이름으로 멤버를 표시합니다. 다음 구문을 사용하여 이러한 멤버를 호출할 수 있습니다. `Class["MemberName"](parameter)`.  
  
     다음 코드에는 두 개의 인터페이스에 Draw 메서드가 있으며 런타임 클래스에서 두 인터페이스를 모두 구현합니다.  
  
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
  
     JavaScript에서 위의 코드를 호출하는 방법을 다음과 같습니다.  
  
    ```JavaScript  
    var example = new ExampleObject();  
    example["CollisionExample.InterfaceA.draw"](12);  
    example["CollisionExample.InterfaceB.draw"]("hello");  
    ```  
  
-   `Out` 매개 변수: Windows 런타임 메서드에 여러 `out` 매개 변수가 있으면, JavaScript의 메서드에는 JavaScript 개체가 반환 값으로 포함되어 있으며 개체에는 `out` 매개 변수에 해당하는 속성이 있습니다. 예를 들어 C++로 된 다음 Windows 런타임 시그니처를 살펴보겠습니다.  
  
    ```cpp#  
    void ExampleMethod(  
      [OutAttribute] char^ first,   
      [OutAttribute] char^ second  
    )  
    ```  
  
     이 시그니처의 JavaScript 버전은 다음과 같습니다.  
  
    ```JavaScript  
    var returnValue = exampleMethod();  
  
    ```  
  
     이 예에서 `returnValue`는 두 개의 필드(`first` 및 `second`)가 있는 JavaScript 개체입니다.  
  
-   정적 멤버: Windows 런타임에서 정적 멤버와 인스턴스 멤버를 정의합니다. 정적 멤버는 JavaScript에서 Windows 런타임 클래스 또는 인터페이스와 연결된 개체에 추가됩니다.  
  
    ```JavaScript  
    // Static method.   
    var accel = Windows.Devices.Sensors.Accelerometer.getDefault();   
    // Instance method.   
    var reading = accel.getCurrentReading();            
    ```  
  
 Windows 런타임 기본 유형의 JavaScript 표시에 대한 자세한 내용은 [Windows 런타임 유형의 JavaScript 표시](../jswinrt/javascript-representation-of-windows-runtime-types.md)를 참조하세요.