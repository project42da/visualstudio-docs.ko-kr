---
title: "IDispatchEx 인터페이스 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- IDispatchEx interface, about IDispatchEx
- IDispatchEx interface
ms.assetid: 37a3303f-f78e-4b5b-aac8-b836c92819de
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9a100a193f5e3abcb076fb8aaf3d64a0d0c38833
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idispatchex-interface"></a>IDispatchEx 인터페이스
`IDispatchEx`의 확장은 `IDispatch` 인터페이스 등 두 가지 스크립팅 언어의 언어와 동적에 적절 한 기능을 지원 합니다. 이 섹션에서는 설명는 `IDispatchEx` 간의 차이점을 자체 인터페이스 `IDispatch` 및 `IDispatchEx`, 및 확장에 대 한 설명입니다. 판독기에 익숙한 것으로 예상 `IDispatch` 고에 대 한 액세스는 `IDispatch` 설명서입니다.  
  
## <a name="remarks"></a>설명  
 `IDispatch`Microsoft Visual Basic에 대해 기본적으로 개발 되었습니다. 에 대 한 기본 제한 `IDispatch` 개체는 정적 가정 한다는 됩니다. 즉, 런타임 중에 개체가 변경 되지 않는 형식 정보 수 완벽 하 게 설명 컴파일 타임에 합니다. Visual Basic Scripting Edition (VBScript)와 같은 스크립팅 언어에 있는 동적 실행 시 모델 및 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 와 동적 HTML 필요한 보다 유연한 인터페이스와 같은 개체 모델입니다.  
  
 `IDispatchEx`모든 서비스를 제공 하기 위해 개발 된 `IDispatch` 적합 한 스크립트 언어와 같은 보다 동적인 런타임에 바인딩된 언어에 대 한 일부 확장 프로그램 및입니다. 추가 기능 `IDispatchEx` 에서 제공 하는 것 이상의 `IDispatch` 됩니다.  
  
-   개체 ("expando")에 새 멤버 추가-사용 하 여 `GetDispID` 와 `fdexNameEnsure` 플래그입니다.  
  
-   개체의 멤버를 삭제 합니다.-사용 하 여 `DeleteMemberByName` 또는 `DeleteMemberByDispID`합니다.  
  
-   대/소문자 구분 디스패치 작업을 사용 하 여 `fdexNameCaseSensitive` 또는 `fdexNameCaseInsensitive`합니다.  
  
-   암시적 이름 가진 멤버에 대 한 검색을 사용 하 여 `fdexNameImplicit`합니다.  
  
-   Dispid 개체의 열거를 사용 하 여 `GetNextDispID`합니다.  
  
-   DISPID에서 요소 이름에 매핑된-사용 하 여 `GetMemberName`합니다.  
  
-   개체 멤버의 속성을 가져오는-사용 하 여 `GetMemberProperties`합니다.  
  
-   메서드를 호출 `this` 포인터-사용 하 여 `InvokeEx` DISPATCH_METHOD 사용 합니다.  
  
-   네임 스페이스를 가져올 개체의 이름 공간 부모의 개념을 지 원하는 브라우저 허용-사용 하 여 `GetNameSpaceParent`합니다.  
  
 개체를 지 원하는 `IDispatchEx` 지원할 수 있습니다 `IDispatch` 이전 버전과 호환성에 대 한 합니다. 지 원하는 개체의 동적 특성 `IDispatchEx` 에 대 한 몇 가지 의미는 `IDispatch` 해당 개체의 인터페이스입니다. 예를 들어 `IDispatch` 다음 가정 합니다.  
  
-   멤버 및 매개 변수 개체의 수명에 대 한 Dispid 상수 상태로 유지 해야 합니다. 이 클라이언트를 Dispid를 한 번 가져온를 캐시 하거나 나중에 사용할 수 있습니다.  
  
 이후 `IDispatchEx` 추가 삭제 유효한 Dispid 집합, 멤버 유지 되지 않는다는 상수를 허용 합니다. 그러나 `IDispatchEx` DISPID 및 멤버 이름 간의 매핑을 그대로 유지 해야 합니다. 즉, 구성원을 삭제 합니다.  
  
-   동일한 이름 가진 멤버를 만들 때까지 DISPID는 재사용할 수 없습니다.  
  
-   DISPID에 대 한 유효한 상태로 유지 되어야 `GetNextDispID`합니다.  
  
-   경우 DISPID를 정상적으로 허용 되어야 합니다는 `IDispatch` 또는 `IDispatchEx` 메서드-삭제 된 것으로 멤버를 인식 하 고 적절 한 오류 코드 (일반적으로 DISP_E_MEMBERNOTFOUND 또는 S_FALSE)를 반환 해야 합니다.  
  
## <a name="examples"></a>예제  
 이 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 함수 test ()의 코드는 다음 작업을 수행 합니다.  
  
-   호출 하 여 새 개체를 만듭니다는 `Object` 생성자 변수 Obj.에 새 개체에 대 한 포인터를 할당 하 고  
  
-   개체의 Elem 이라는 새 요소를 만들고 함수 cat에 대 한 포인터를이 요소에 할당 합니다.  
  
-   이 함수를 호출 합니다. 를 사용 하는 방법으로 호출 하므로 `this` 포인터가 Obj. 개체 참조 새 요소를 추가 하는 함수 개체의 모음입니다.  
  
 전체 HTML 코드는입니다.  
  
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
  
 이 같은 웹 페이지에 배치 되는 컨트롤은 브라우저에서 스크립트 엔진에 디스패치 포인터를 얻을 수 있습니다. 컨트롤 함수 test ()를 구현 다음 수 없습니다.  
  
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
  
 컨트롤에서 발생 한 코드, 테스트와 동일한 작업을 수행 된 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 함수 `test()`합니다. 이러한 디스패치 호출이 실행에 수행 되는 참고 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 엔진 및 엔진의 상태를 변경 합니다.  
  
-   사용 하 여 cat 함수에 디스패치 포인터를 가져옵니다 `GetDispID()`합니다.  
  
-   사용 하 여 개체 함수에 디스패치 포인터를 가져옵니다 `GetDispID()`합니다.  
  
-   개체를 사용 하 여 개체 함수를 호출 하 여 생성 `InvokeEx()` 하 고 새로 생성 된 개체에 대 한 디스패치 포인터를 가져옵니다.  
  
-   Elem, 새 요소를 사용 하 여 개체에 만듭니다 `GetDispID()` 와 `fdexNameEnsure` 플래그입니다.  
  
-   디스패치 파일에 대 한 포인터 저장 되며, 사용 하 여 요소에서 cat에 `InvokeEx()`합니다.  
  
-   메서드로 디스패치 포인터 cat를 호출 하 여 호출 `InvokeEx()` 으로 생성 된 개체에 디스패치 파일에 대 한 포인터를 전달 하 고는 `this` 포인터입니다.  
  
-   Cat 메서드가 만드는 새 요소를 현재 모음 `this` 개체입니다.  
  
-   확인 하는 새 요소가 가로 막대형,에서 만든 생성된 된 개체를 사용 하 여 요소를 열거 하 여 `GetNextDispID()`합니다.  
  
 테스트 컨트롤에 대 한 코드:  
  
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
  
## <a name="methods"></a>메서드  
 [IDispatchEx 메서드](../../winscript/reference/idispatchex-methods.md)