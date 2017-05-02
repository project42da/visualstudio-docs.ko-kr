---
title: "Edge 및 레거시 엔진을 대상으로 지정 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: cbc7df6c-0bc9-48f5-b9ad-b9ed31c42f92
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# Edge 및 레거시 엔진을 대상으로 지정
Windows 10부터 새 Edge 렌더링 엔진을 지원하는 Windows 10 브라우저 전략에 맞춰 Chakra\(JavaScript 엔진\)에서 변경한 내용 중 하나는 다음 두 개의 서로 다른 Chakra 엔진을 지원하는 것입니다.  
  
-   Internet Explorer 11과 함께 제공되고 지원하는 이전 Chakra 엔진\(아래에서 *레거시 엔진* 또는 jscript9.dll이라고도 함\). 이 엔진은 시간이 지나도 고정되며 Win8.1\/IE11 릴리스에서 근본적으로 변경되지 않습니다.  
  
-   Windows 10의 새 브라우저인 Microsoft Edge와 함께 제공되고 지원하는 새로운 Chakra 엔진\(아래에서 *Edge 엔진* 또는 chakra.dll이라고도 함\). 이 엔진은 지속적으로 업데이트되고 "살아있는" [Edge\(가장자리\)](http://blogs.msdn.com/b/ie/archive/2014/11/11/living-on-the-edge-our-next-step-in-interoperability.aspx) 엔진을 지원합니다. 살아 있는 Edge 엔진은 레거시 엔진과 달리 Edge 엔진이 옵트인\(opt in\)할 버전 관리 스크립트 기능 형식을 전달하지 않음을 의미합니다.  
  
 JsRT\(JavaScript 런타임 호스팅\) API를 사용하여 앱을 만드는 경우 레거시 또는 Edge 엔진 중 하나를 대상으로 지정할 수 있습니다.  
  
-   기존 응용 프로그램의 이전 버전과 호환성을 강조해야 하는 경우 레거시 엔진을 대상으로 지정합니다.  
  
-   앱에서 미래 지향적으로, 릴리스되는 새로운 JavaScript 기능\(예: ECMAScript 6\)을 지원하려는 경우 Edge 엔진을 대상으로 지정합니다.  
  
 이 항목에는 서로 다른 엔진을 대상으로 지정하는 방법을 설명하는 세부 정보가 포함되어 있습니다.  
  
## 기본 설정된 버전을 대상으로 지정  
 앱을 만들 때 Edge 엔진 또는 레거시 엔진을 지원하는 JsRT 버전을 선택할 수 있습니다. 위의 지침에 따라 JsRT 버전을 선택할 수 있습니다. 이러한 차이를 수용하기 위해 `JsCreateRuntime`, `JsCreateContext` 및 `JsStartDebugging`이 다음과 같이 변경되었습니다.  
  
 `JsCreateRuntime`의 경우:  
  
-   레거시 엔진을 대상으로 지정하는 경우 `JsRuntimeVersionEdge` 열거형 값이 사용되지 않고 `JsRuntimeVersionInternetExplorer11` 값을 대신 사용하도록 제안하는 메시지가 표시됩니다.  
  
-   Edge 엔진을 대상으로 지정하는 경우 `JsCreateRuntime` 함수에서 version 매개 변수가 생략됩니다.  
  
    ```cpp  
    JsErrorCode JsCreateRuntime(JsRuntimeAttributes attributes, JsThreadServiceCallback callback, _Out_ JsRuntimeHandle* runtime);  
    ```  
  
 `JsCreateContext` 및 `JsStartDebugging`의 경우:  
  
-   레거시 엔진을 대상으로 지정하는 경우 `IDebugApplication` 인터페이스가 원격이 아닌 고유한 디버깅 메서드를 제공하는 데 사용됩니다. 디버깅을 위해 `JsCreateContext` 및 `JsStartDebugging` 함수는 `IDebugApplication`을 매개 변수로 사용합니다.  
  
-   Edge 엔진을 대상으로 지정하는 경우 `IDebugApplication` 인터페이스가 사용되지 않습니다. Chakra 엔진에서는 사용자가 `IDebugApplication`을 구현할 필요 없이 Visual Studio 디버거를 통해 네이티브 및 스크립트 디버깅 기능을 사용할 수 있습니다. 인터페이스가 더 이상 결과인 `JsCreateContext` 및 `JsStartDebugging`의 매개 변수가 아닙니다.  
  
 레거시 엔진에서 이전 API에 대한 서명은 다음과 같습니다.  
  
```cpp  
JsErrorCode JsCreateRuntime(JsRuntimeAttributes attributes, JsRuntimeVersion version, JsThreadServiceCallback callback, _Out_ JsRuntimeHandle* runtime);  
  
JsErrorCode JsCreateContext(JsRuntimeHandle runtime, IDebugApplication *debugApplication, JsContextRef *newContext);  
  
JsErrorCode JsStartDebugging(IDebugApplication *debugApplication);  
```  
  
 Edge 엔진에서 이전 API에 대한 서명은 다음과 같습니다.  
  
```cpp  
JsErrorCode JsCreateRuntime(JsRuntimeAttributes attributes, JsThreadServiceCallback callback, _Out_ JsRuntimeHandle* runtime);  
  
JsErrorCode JsCreateContext(JsRuntimeHandle runtime, JsContextRef *newContext);  
  
JsErrorCode JsStartDebugging();  
```  
  
## Visual C\+\+를 사용하여 기본 설정된 버전에 대해 컴파일  
 Visual C\+\+를 사용하는 경우 jsrt.h 헤더를 포함하여 JsRT API를 가져오고 jsrt.lib가 링커 입력 파일 목록에 포함되었는지 확인합니다.  
  
```cpp  
#include <jsrt.h>  
```  
  
 ![링커 입력 파일로 jsrt.lib 추가](../chakra-hosting/media/js-chakra.png "JS\_Chakra\_")  
  
 Edge 엔진 이진 파일을 대상으로 지정하려는 경우 jsrt.h를 포함하기 전에 `USE_EDGEMODE_JSRT` 매크로를 정의해야 하며, jsrt.lib에 대해 연결하는 대신 chakrart.lib에 대해 연결해야 합니다.  
  
```cpp  
#define USE_EDGEMODE_JSRT  
#include <jsrt.h>  
```  
  
 ![링커 입력 파일로 chakrart.lib 추가](../chakra-hosting/media/js-chakra-hosting.png "JS\_Chakra\_Hosting\_")  
  
 새 응용 프로그램으로 시작하는 경우 이제 JsRT API에 대한 코드 작성을 시작할 준비가 되었습니다.  
  
## .NET을 사용하여 기본 설정된 버전에 대해 컴파일  
 .NET 및 P\/Invoke를 사용하는 경우 jscript9.dll 대신 chakra.dll을 가져오도록 JsRT API \[DllImport\] 선언을 변경해야 합니다. 또한 `JsCreateRuntime`의 정의를 변경하여 `JsRuntimeVersion` 매개 변수를 제거하고, `JsCreateContext` 및 `JsStartDebugging`의 정의를 변경하여 `IDebugApplication` 매개 변수를 제거합니다.  
  
 레거시 엔진의 경우 다음 코드를 사용합니다.  
  
```csharp  
[DllImport("jscript9.dll")]  
public static extern JsErrorCode JsCreateRuntime(  
    JsRuntimeAttributes attributes,  
    JsRuntimeVersion version,  
    JsThreadServiceCallback callback,  
    out JsRuntimeSafeHandle runtime  
);  
  
[DllImport("jscript9.dll")]  
public static extern JsErrorCode JsCreateContext(  
    JsRuntimeSafeHandle runtime,  
    IDebugApplication debugApplication,  
    out JsContextRef newContext  
);   
  
[DllImport("jscript9.dll")]  
public static extern JsErrorCode JsStartDebugging(  
    IDebugApplication debugApplication,  
);  
```  
  
 Edge 엔진의 경우 다음 코드를 사용합니다.  
  
```csharp  
[DllImport("chakra.dll")]  
public static extern JsErrorCode JsCreateRuntime(  
    JsRuntimeAttributes attributes,  
    JsThreadServiceCallback callback,  
    out JsRuntimeSafeHandle runtime  
);  
  
[DllImport("chakra.dll")]  
public static extern JsErrorCode JsCreateContext(  
    JsRuntimeSafeHandle runtime,  
    out JsContextRef newContext  
);   
  
[DllImport("chakra.dll")]  
public static extern JsErrorCode JsStartDebugging();  
```  
  
> [!CAUTION]
>  함수 포인터를 수동으로 마샬링하는 경우\(예: LoadLibrary\/GetProcAddress를 통해\) 메서드 선언을 혼합하지 않는 것이 중요합니다. 그렇지 않으면 스택의 균형이 깨어져 앱에서 충돌 발생과 같은 예기치 않은 동작이 발생합니다. 가져오기 코드에서 jscript9.dll 인스턴스에 대해 전체 검색 및 바꾸기를 수행하는 경우 삭제되는 `version` 매개 변수가 누락되기 때문에 동일한 문제가 발생합니다.  
  
## 요약  
 Windows 10에서 JavaScript 런타임 호스팅 API는 두 개로 분할됩니다. 이러한 API는 이제 언어 기능이 Microsoft Edge의 "살아 있는" Edge 엔진과 맞춰지는 "살아 있는" Edge 엔진을 지원합니다. 데스크톱 또는 스토어 앱에서 이러한 기능을 활용하여 응용 프로그램을 확장하고 기존 코드베이스에서 최신 웹 기술을 활용하는 새롭고 흥미로운 방법을 만들 수 있습니다. 그러나 이전 버전 간에 미묘한 차이가 있기 때문에 Edge 또는 레거시 엔진을 대상으로 지정할 때 다음 사항에 주의해야 합니다.  
  
-   앱에서 프로세스마다 JsRT의 버전을 하나만 지원할 수 있습니다.  
  
     예를 들어 Edge 엔진 런타임을 만든 다음 레거시 엔진 런타임을 만들고 동일한 프로세스에서 올바르게 실행될 것을 기대할 수 없습니다. 이 기능은 지원되지 않으며 두 번째 DLL 로드 실패와 같은 문서화되지 않은 동작이 발생할 수 있습니다.  
  
-   Edge 엔진을 대상으로 지정하는 경우 기본 플랫폼이 자동으로 업데이트될 때 앱이 새로운 기능을 예기치 않게 얻을 수도 있습니다.  
  
     예를 들어 레거시 런타임의 Internet Explorer 11 모드에서는 `let` 및 `const`와 같은 블록 범위 변수 선언을 지원합니다. Edge 엔진 자동 버전 관리 동작이 이전에 표준이었다면 블록 범위 규칙이 없는 Internet Explorer 10 모드로 작업된 코드는 플랫폼이 자동으로 업그레이드될 때 실패하기 시작할 수 있습니다. 사용할 런타임 모델을 선택할 때 이 점을 고려해야 합니다. 가능하면 Edge 엔진을 대상으로 지정해야 하지만 나중에 무효화될 수 있는 JavaScript 코드 구조의 사용에 대해 주의해야 합니다.  
  
-   Windows 스토어용 JsRT는 Edge 엔진\(chakra.dll\)만 지원합니다. jscript9.dll의 JsRT API에 대해 연결을 시도하는 앱은 인증에 실패합니다.  
  
-   jscript9.dll과 chakra.dll 간에 `JsCreateRuntime`, `JsCreateContext` 및 `JsStartDebugging` 선언을 혼동하지 않는 것이 중요합니다. 혼동할 경우 스택의 균형이 깨어집니다.  
  
     C 및 C\+\+를 사용하는 경우 `LoadLibrary`와 `GetProcAddress`를 차례로 호출하는 것과 같은 작업을 수행하지 않는 한 잘못된 선언을 사용하려고 하면 링커 오류가 발생합니다. .NET 개발자는 이 문제를 쉽게 찾지 못할 수 있으므로 이 기능을 사용할 때는 코드를 다시 확인합니다.  
  
## 참고 항목  
 [JavaScript 런타임 호스팅](../chakra-hosting/javascript-runtime-hosting.md)