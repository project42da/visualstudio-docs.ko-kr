---
title: "IDispatchEx 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IDispatchEx 인터페이스"
  - "IDispatchEx 인터페이스, IDispatchEx 정보"
ms.assetid: 37a3303f-f78e-4b5b-aac8-b836c92819de
caps.latest.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 12
---
# IDispatchEx 인터페이스
`IDispatchEx`확장은 `IDispatch` 인터페이스를 지 원하는 기능 적절 한 스크립트 언어와 같은 동적 언어에 대 한.  설명의 `IDispatchEx` 자체의 차이점을 인터페이스 `IDispatch` 및 `IDispatchEx`, 및 확장에 대 한 근거 합니다.  판독기를 알고 있는 것이 야 `IDispatch` 액세스할 수 있는 `IDispatch` 설명서.  
  
## 설명  
 `IDispatch`기본적으로 Microsoft Visual Basic 대 한 개발 되었습니다.  기본 제한의 `IDispatch` 개체 정적으로 간주 하는 것입니다.  런타임에 개체가 변경 되지 않는 있으므로 즉, 형식 정보 완전히를 컴파일 타임에 설명할 수 있습니다.  Visual Basic Scripting Edition \(VBScript\) 스크립트 언어에 있는 동적 런타임 모델 및 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 및 동적 HTML과 같이 융통성 있는 인터페이스 개체를 모델링 합니다.  
  
 `IDispatchEx`모든 서비스를 제공 하기 위해 개발 되었습니다 `IDispatch` 와 같은 스크립트 언어 보다 동적 런타임에 바인딩된 언어에 일부 확장 합니다.  추가 기능을 `IDispatchEx` 외 제공 `IDispatch` 됩니다.  
  
-   \("Expando"\) 개체에 새 구성원 추가\-사용 `GetDispID` 에 `fdexNameEnsure` 플래그.  
  
-   개체의 멤버를 삭제\-사용 `DeleteMemberByName` 또는 `DeleteMemberByDispID`.  
  
-   대\/소문자 구분 발송 작업\-사용 `fdexNameCaseSensitive` 또는 `fdexNameCaseInsensitive`.  
  
-   이름의 암시적 멤버를 검색, 사용 `fdexNameImplicit`.  
  
-   열거 개체에 대 한 Dispid\-사용 `GetNextDispID`.  
  
-   DISPID 맵에서 요소 이름 — 사용 `GetMemberName`.  
  
-   구성원 개체의 등록 정보\-사용 `GetMemberProperties`.  
  
-   메서드 호출에 `this` 포인터\-사용 `InvokeEx` DISPATCH\_METHOD 사용 합니다.  
  
-   이름 공간 부모 개체를 얻을 수 있는 네임 스페이스의 개념을 지 원하는 브라우저 허용\-사용 `GetNameSpaceParent`.  
  
 지원 개체 `IDispatchEx` 도 없는데 `IDispatch` 이전 버전과 호환성.  지원 되는 개체의 동적 특성 `IDispatchEx` 에 몇 가지 의미가 있는 `IDispatch` 해당 개체의 인터페이스.  예를 들어, `IDispatch` 다음 가정 합니다.  
  
-   Dispid 멤버 및 매개 변수 개체의 수명에 대 한 상수 유지 되어야 합니다.  이 번 Dispid를 얻기를 나중에 사용할 수 있도록 캐시 하는 클라이언트 수 있습니다.  
  
 이후 `IDispatchEx` 추가 및 구성원 집합이 올바른 Dispid 삭제 하지 않습니다 남아 상수 있습니다.  그러나 `IDispatchEx` DISPID 및 구성원 이름 간의 매핑을 상수 상태로 유지 되어야 합니다.  즉 멤버를 삭제 하는 경우:  
  
-   동일한 이름의 멤버를 만들 때까지 DISPID는 재사용할 수 없습니다.  
  
-   DISPID는 유효한 남아 있어야 `GetNextDispID`.  
  
-   DISPID는 정상적으로 동의 해야는 `IDispatch` 또는 `IDispatchEx` 메서드\-멤버 삭제 된 것으로 인식 하 고 \(일반적으로 DISP\_E\_MEMBERNOTFOUND 또는 S\_FALSE\)는 적절 한 오류 코드를 반환 해야 합니다.  
  
## 예제  
 이 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 코드 함수 test \(\)에서 다음 작업을 합니다.  
  
-   호출 하 여 새 개체를 만듭니다는 `Object` 생성자에 포인터 변수 사항은.obj에 새 개체를 할당 하 고  
  
-   Elem 개체의 명명 된 새 요소를 만듭니다 및이 요소에 함수 고양이에 대 한 포인터를 할당 합니다.  
  
-   이 함수를 호출합니다.  이 메서드를 호출 하기 때문에 `this` 포인터가 참조 사항은.obj 개체에  함수에 새 요소 추가 개체의 모음입니다.  
  
 전체 HTML 코드는 다음과 같습니다.  
  
```  
<html>  
<body>  
<script type="text/javascript">  
function cat()  
{  
   // Create new element and assign the value 10  
   this.Bar = 10;  
}  
  
function test()  
{  
   // Construct new object  
   Obj = new Object();  
  
   // Create new element and assign function pointer  
   Obj.Elem = cat;  
  
   // Call Elem method ("this" == Obj)  
   Obj.Elem();  
  
   // Obj.Bar now exists  
}  
test();  
</script>  
</body>  
</html>  
```  
  
 이 같은 웹 페이지에 있는 컨트롤 디스패치 포인터 브라우저에서 스크립트 엔진을 얻을 수 있습니다.  다음 컨트롤 함수 test \(\)를 구현할 수 있습니다.  
  
```  
<html>  
<body>  
<script type="text/javascript">  
function cat()  
{  
   // Create new element and assign the value 10  
   this.Bar = 10;  
}  
</script>  
<object id="test" <CLASSID="CLSID:9417DB5D-FA2A-11D0-8CB3-00C04FC2B085">>  
</object>  
</body>  
</html>  
```  
  
 컨트롤의 코드, 테스트, 동일 하지는 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 함수 `test()`.  참고 이러한 디스패치 호출 실행에 대해 하 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 엔진과 엔진의 상태를 변경 합니다.  
  
-   Cat 함수 사용 디스패치 포인터를 얻는 `GetDispID()`.  
  
-   사용 하 여 개체 함수 디스패치 포인터를 얻는 `GetDispID()`.  
  
-   개체 함수를 호출 하 개체 생성 `InvokeEx()` 및 새로 생성 된 개체에 대 한 디스패치 포인터를 가져옵니다.  
  
-   요소에 새 요소는 개체를 사용 하 여 만드는 `GetDispID()` 에 `fdexNameEnsure` 플래그.  
  
-   디스패치 포인터 cat을 사용 하 여 요소를 배치 `InvokeEx()`.  
  
-   방법으로 호출 하 여 cat 디스패치 포인터를 호출 `InvokeEx()` 및 디스패치 포인터에서 생성 된 개체에 전달 된 `this` 포인터.  
  
-   Cat 메서드는 새 요소를 만든 모음의 현재 `this` 개체입니다.  
  
-   확인 하는 새 요소 막대에서 생성 된 개체를 사용 하 여 요소를 열거 하 여 만든 `GetNextDispID()`.  
  
 테스트 컨트롤의 코드:  
  
```  
   BOOL test(IDispatchEx *pdexScript)  
   {  
      HRESULT hr;  
      VARIANT var;  
      DISPID dispid, putid;  
      BOOL retval = FALSE;  
      BSTR bstrName = NULL;  
      IDispatch   *pdispObj = NULL, *pdispCat = NULL;  
      IDispatchEx *pdexObj = NULL;  
      DISPPARAMS dispparams, dispparamsNoArgs = {NULL, NULL, 0, 0};  
  
      // Get dispatch pointer for "cat"  
      bstrName = SysAllocString(OLESTR("cat"));  
         if (bstrName == NULL) goto LDone;  
      hr = pdexScript->GetDispID(bstrName, 0, &dispid);  
         if (FAILED(hr)) goto LDone;  
      SysFreeString(bstrName);  
         bstrName = NULL;  
      hr = pdexScript->InvokeEx(dispid, LOCALE_USER_DEFAULT,   
         DISPATCH_PROPERTYGET, &dispparamsNoArgs,   
         &var, NULL, NULL);  
         if (FAILED(hr)) goto LDone;  
      pdispCat = var.pdispVal;  
  
      // Create object by calling "Object" constructor  
      bstrName = SysAllocString(OLESTR("Object"));  
         if (NULL == bstrName) goto LDone;  
      hr = pdexScript->GetDispID(bstrName, 0, &dispid);  
         if (FAILED(hr)) goto LDone;  
      SysFreeString(bstrName);  
         bstrName = NULL;  
      hr = pdexScript->InvokeEx(dispid, LOCALE_USER_DEFAULT,   
         DISPATCH_CONSTRUCT, &dispparamsNoArgs,   
         &var, NULL, NULL);  
         if (FAILED(hr)) goto LDone;  
      pdispObj = var.pdispVal;  
      hr = pdispObj->QueryInterface(IID_IDispatchEx, (void **)&pdexObj);  
         if (FAILED(hr)) goto LDone;  
  
      // Create new element in object  
      bstrName = SysAllocString(OLESTR("Elem"));  
         if (NULL == bstrName) goto LDone;  
      hr = pdexObj->GetDispID(bstrName, fdexNameEnsure, &dispid);  
         if (FAILED(hr)) goto LDone;  
      SysFreeString(bstrName);  
         bstrName = NULL;  
  
      // Assign "cat" dispatch pointer to element  
      putid = DISPID_PROPERTYPUT;  
      var.vt = VT_DISPATCH;  
      var.pdispVal = pdispCat;  
      dispparams.rgvarg = &var;  
      dispparams.rgdispidNamedArgs = &putid;  
      dispparams.cArgs = 1;  
      dispparams.cNamedArgs = 1;  
      hr = pdexObj->InvokeEx(dispid, LOCALE_USER_DEFAULT,   
         DISPATCH_PROPERTYPUTREF, &dispparams,  
         NULL, NULL, NULL);  
         if (FAILED(hr)) goto LDone;  
  
      // Invoke method with "this" pointer  
      putid = DISPID_THIS;  
      var.vt = VT_DISPATCH;  
      var.pdispVal = pdispObj;  
      dispparams.rgvarg = &var;  
      dispparams.rgdispidNamedArgs = &putid;  
      dispparams.cArgs = 1;  
      dispparams.cNamedArgs = 1;  
      hr = pdexObj->InvokeEx(dispid, LOCALE_USER_DEFAULT,  
         DISPATCH_METHOD, &dispparams,  
            NULL, NULL, NULL);  
         if (FAILED(hr)) goto LDone;  
  
      // Confirm that new element "Bar" is in object  
      hr = pdexObj->GetNextDispID(fdexEnumAll, DISPID_STARTENUM, &dispid);  
      while (hr == NOERROR)  
      {  
            hr = pdexObj->GetMemberName(dispid, &bstrName);  
            if (FAILED(hr)) goto LDone;  
            retval = !wcscmp(bstrName, OLESTR("Bar"));  
            SysFreeString(bstrName);  
            bstrName = NULL;  
            if (retval) goto LDone;  
         hr = pdexObj->GetNextDispID(fdexEnumAll, dispid, &dispid);  
      }  
LDone:  
   SysFreeString(bstrName);  
   if (pdispCat != NULL)  
      pdispCat->Release();  
   if (pdispObj != NULL)  
      pdispObj->Release();  
   if (pdexObj != NULL)  
      pdexObj->Release();  
  
   return retval;  
   }  
```  
  
## 메서드  
 [IDispatchEx 메서드](../../winscript/reference/idispatchex-methods.md)