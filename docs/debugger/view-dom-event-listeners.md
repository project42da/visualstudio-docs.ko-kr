---
title: "DOM 이벤트 수신기 보기 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "DOM 이벤트, 보기[Windows 스토어 앱]"
  - "이벤트 수신기, 보기[Windows 스토어 앱]"
ms.assetid: d5b679e7-87dd-4cec-9176-883db6ff0781
caps.latest.revision: 23
caps.handback.revision: 23
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# DOM 이벤트 수신기 보기
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

![Windows 및 Windows Phone에 적용](~/docs/debugger/media/windows_and_phone_content.png "windows\_and\_phone\_content")  
  
 DOM 탐색기의 **이벤트** 탭에는 DOM 요소와 연결된 이벤트가 표시됩니다. **이벤트** 탭에 있는 각각의 최상위 노드는 활성 구독자가 있는 이벤트를 나타냅니다. 최상위 노드에는 특정 이벤트에 대해 등록된 이벤트 수신기를 나타내는 하위 노드가 포함되어 있습니다. 이벤트를 수신기를 볼 수 있을뿐 아니라 이 탭을 사용하여 JavaScript 코드에서 이벤트 수신기 위치를 탐색할 수도 있습니다. 이 항목의 내용은 HTML 및 JavaScript로 작성된 스토어 앱에 적용됩니다.  
  
 **이벤트** 탭의 목록은 동적입니다. 앱 실행 중에 이벤트 수신기를 추가하면 목록에 새 이벤트 수신기가 나타납니다. 이벤트 수신기 추가 및 제거에 대한 자세한 내용은 이 항목의 [이벤트 수신기 관련 문제 해결을 위한 팁](#Tips)을 참조하십시오.  
  
> [!NOTE]
>  DOM 요소가 아닌 `xhr`과 같은 코드 요소에 대한 이벤트 수신기는 **이벤트** 탭에 나타나지 않습니다.  
  
## DOM 요소의 이벤트 수신기 보기  
 이 예에는 Windows Phone 스토어 앱이 나와 있습니다. 여기서 설명하는 DOM 탐색기 기능은 Windows 스토어 앱에서도 지원됩니다.  
  
#### 이벤트 수신기를 보려면  
  
1.  Visual Studio에서 Windows Phone 피벗 응용 프로그램 프로젝트 템플릿을 사용하는 JavaScript 앱을 만듭니다.  
  
2.  Visual Studio에서 이 템플릿을 열어 둔 상태로 디버거의 디버그 도구 모음에 있는 드롭다운 목록에서 **에뮬레이터 8.1 WVGA 4인치 512MB**를 선택합니다.  
  
     ![디버그 대상 선택](../debugger/media/js_dom_debug_target_emu.png "JS\_DOM\_Debug\_Target\_Emu")  
  
3.  F5 키를 눌러 디버그 모드에서 응용 프로그램을 실행합니다.  
  
4.  실행 중인 앱에서 **섹션 3** 피벗 항목으로 이동합니다.  
  
5.  Visual Studio로 전환합니다\(Alt\+Tab 또는 F12\).  
  
6.  DOM 탐색기의 오른쪽 상단에 있는 `Find`를 선택합니다.  
  
7.  `ListView`를 입력한 후 Enter 키를 누릅니다.  
  
8.  필요하면 **다음** 단추를 선택하여 `ListView` 컨트롤을 나타내는 `DIV` 요소를 찾습니다\(이 요소에는 `WinJS.UI.ListView`의 `data-win-control` 값이 있음\).  
  
     이제 DOM 탐색기에서 `DIV` 요소를 선택할 수 있습니다.  
  
9. DOM 탐색기의 오른쪽 창에서 **이벤트** 탭을 선택합니다.  
  
     이제 다음과 같이 `DIV` 요소에 대한 활성 구독자가 있는 이벤트를 볼 수 있습니다.  
  
     ![DOM 탐색기의 이벤트 탭](../debugger/media/js_dom_events.png "JS\_DOM\_Events")  
  
10. 이러한 이벤트에 대한 이벤트 수신기를 찾으려면 연결된 JavaScript 파일 링크를 선택합니다.  
  
11. DOM 계층 구조에서 부모 요소에 대한 이벤트 수신기를 신속하게 식별하려면 DOM 탐색기의 맨 아래 있는 계층 구조 목록에서 부모 요소를 선택합니다.  
  
     ![DOM 계층에서 상위 요소 선택](~/docs/debugger/media/js_dom_breadcrumbs.png "JS\_DOM\_Breadcrumbs")  
  
     **이벤트** 탭에는 계층 구조 목록에서 선택한 모든 요소의 이벤트 수신기가 표시됩니다.  
  
###  <a name="Tips"></a> 이벤트 수신기 관련 문제 해결을 위한 팁  
 일부 앱 시나리오에서는 [removeEventListener](http://msdn.microsoft.com/library/ie/ff975250\(v=vs.85\).aspx)를 사용하여 이벤트 수신기를 명시적으로 제거해야 합니다. DOM 탐색기에서 **이벤트** 탭을 사용하여 코드 실행 중 DOM 요소에서 이벤트 수신기가 제거되었는지 여부를 테스트합니다. 아래 이러한 유형의 문제를 해결할 수 있는 팁이 몇 가지 나와 있습니다.  
  
-   Visual Studio [프로젝트 템플릿](http://msdn.microsoft.com/library/windows/apps/hh758331.aspx)으로 구현된 단일 페이지 탐색 모델을 사용하는 앱의 경우 일반적으로 페이지의 일부인 개체\(예: DOM 요소\)에 대해 등록된 이벤트 수신기를 제거할 필요가 없습니다. 이 시나리오에서 DOM 요소 및 연결된 이벤트 수신기는 수명이 동일하고 가비지 수집될 수 있습니다.  
  
-   DOM 요소 또는 개체의 수명이 연결된 수신기와 다르면 `removeEventListener` 메서드를 호출해야 할 수 있습니다. 예를 들어 `window.onresize` 이벤트를 사용하는 경우 이벤트를 처리하는 페이지를 벗어나 탐색하면 이벤트 수신기를 제거해야 할 수 있습니다.  
  
-   `removeEventListener`가 지정된 수신기를 제거하지 못할 경우 개체의 다른 인스턴스에서 호출되고 있는 중일 수 있습니다. 수신기 추가 시 [bind 메서드\(Function\)](../Topic/bind%20Method%20\(Function\)%20\(JavaScript\).md) 메서드를 사용하여 이 문제를 해결할 수 있습니다.  
  
-   [bind 메서드\(Function\)](../Topic/bind%20Method%20\(Function\)%20\(JavaScript\).md) 또는 익명 함수를 사용하여 추가된 이벤트 수신기를 제거하려면 수신기를 추가할 때 함수의 인스턴스를 저장합니다. 아래 이러한 패턴을 안전하게 사용하는 방법이 한 가지 나와 있습니다.  
  
    ```javascript  
    // You could use the following code within the constructor function of an object, or  
    // in the ready function of a PageControl object (Store app).  
    this.storedHandler = this._handlerFunc.bind(this);  
    elem.addEventListener('mouseup', this.storedHandler);  
  
    // In this example, add the following code in the PageControl object's unload function.  
    elem.removeEventListener('mouseup', this.storedHandler);  
  
    ```  
  
     바인딩된 함수에 참조를 저장하는 대신 다음 코드를 사용할 경우 이벤트 수신기를 명시적으로 제거하지 못할 수 있습니다.  
  
    ```javascript  
    // Avoid this pattern. No reference to the bound function is available.  
    elem.addEventListener('mouseup', this._handlerFunc.bind(this));  
    ```  
  
-   `obj.on<eventname>` 특성\(예: `window.onresize = handlerFunc`\)을 사용하여 이벤트 수신기를 추가한 경우에는 `removeEventListener`를 사용하여 제거할 수 없습니다.  
  
-   앱의 [JavaScript 메모리](../profiling/javascript-memory.md)에 JavaScript 메모리 분석기를 사용합니다. 명시적으로 제거해야 하는 이벤트 수신기는 메모리 누수로 나타날 수 있습니다.  
  
## 참고 항목  
 [퀵 스타트: HTML 및 CSS 디버그](../debugger/quickstart-debug-html-and-css.md)   
 [DOM 탐색기를 사용하여 CSS 스타일 디버그](../debugger/debug-css-styles-using-dom-explorer.md)   
 [DOM 탐색기를 사용하여 레이아웃 디버깅](../debugger/debug-layout-using-dom-explorer.md)