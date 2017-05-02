---
title: "IDispatchEx::InvokeEx | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDispatchEx.InvokeEx
apilocation: scrobj.dll
helpviewer_keywords: 
  - "InvokeEx 메서드"
ms.assetid: d90783e6-4b89-4423-8a56-a9c8b4b2c813
caps.latest.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 10
---
# IDispatchEx::InvokeEx
액세스할 속성 및 메서드를 노출 하는 `IDispatchEx` 개체입니다.  
  
## 구문  
  
```  
HRESULT InvokeEx(  
   DISPID id,  
   LCID lcid,  
   WORD wFlags,  
   DISPARAMS *pdp,  
   VARIANT *pVarRes,   
   EXCEPINFO *pei,   
   IServiceProvider *pspCaller   
);  
```  
  
#### 매개 변수  
 `id`  
 멤버를 식별합니다.  사용 하 여 `GetDispID` 또는 `GetNextDispID` 디스패치 식별자를 얻을 수 있습니다.  
  
 `lcid`  
 인수를 해석할 로캘 컨텍스트입니다.  `lcid` 전달 된 `InvokeEx` 개체의 로케일에 따라 인수를 해석할 수 있도록 합니다.  
  
 `wFlags`  
 법적 값에 대 한 `wFlags` 입니다.  
  
 DISPATCH\_PROPERTYGET &#124; DISPATCH\_METHOD &#124; DISPATCH\_PROPERTYPUT &#124; DISPATCH\_PROPERTYPUTREF &#124; DISPATCH\_CONSTRUCT  
  
 컨텍스트를 설명 하는 플래그는 `InvokeEx` 를 호출 합니다.  
  
|값|의미|  
|-------|--------|  
|DISPATCH\_METHOD|멤버를 메서드로 호출 됩니다.  속성 이름이 동일한 경우이 고 DISPATCH\_PROPERTYGET 플래그를 모두 설정할 수 있습니다 \(정의 `IDispatch`\).|  
|DISPATCH\_PROPERTYGET|멤버를 속성이 나 데이터 멤버로 검색 \(정의 `IDispatch`\).|  
|DISPATCH\_PROPERTYPUT|멤버를 속성이 나 데이터 멤버로 변경 \(정의 `IDispatch`\).|  
|DISPATCH\_PROPERTYPUTREF|값 할당 대신 참조 할당 된 멤버를 변경 합니다.  만 참조 하는 개체의 속성에 사용할 때이 플래그가 잘못 되었습니다 \(정의 `IDispatch`\).|  
|DISPATCH\_CONSTRUCT|멤버는 생성자로 사용 중입니다.  \(이 새 값에 의해 정의 된 `IDispatchEx`\).  법적 값에 대 한 `wFlags` 입니다.<br /><br /> DISPATCH\_PROPERTYGET DISPATCH\_METHOD DISPATCH\_PROPERTYPUT DISPATCH\_PROPERTYPUTREF DISPATCH\_CONSTRUCT|  
  
 `pdp`  
 인수의 배열, 명명된 인수에 대한 인수 DISPID의 배열 및 배열에 있는 요소의 개수가 들어 있는 구조체에 대한 포인터입니다.  참조는 `IDispatch` DISPPARAMS 구조에 대 한 자세한 내용은 설명서.  
  
 `pVarRes`  
 결과 호출자 결과가 필요한 경우에 Null 또는 저장 될 위치에 포인터입니다.  DISPATCH\_PROPERTYPUT 또는 DISPATCH\_PROPERTYPUTREF를 지정 하면이 인수는 무시 됩니다.  
  
 `pei`  
 예외 정보가 포함된 구조체에 대한 포인터입니다.  이 구조체에 채우는 `DISP_E_EXCEPTION` 이 반환 됩니다.  Null이 될 수 있습니다.  참조는 `IDispatch` 에 대 한 자세한 내용은 설명서의 `EXCEPINFO` 구조.  
  
 `pspCaller`  
 개체 서비스에서 호출자를 얻을 수 있는 호출자가 제공한 서비스 공급자 개체에 대 한 포인터입니다.  Null이 될 수 있습니다.  
  
 `IDispatchEx::InvokeEx`같은 기능을 제공 `IDispatch::Invoke` 및 몇 가지 확장을 추가 합니다.  
  
|||  
|-|-|  
|DISPATCH\_CONSTRUCT|항목 생성자로 사용 되 고 있음을 나타냅니다.|  
|`pspCaller`|`pspCaller` 호출자가 제공 하는 서비스에 대 한 개체 액세스를 허용 합니다.  특정 서비스 호출자가 처리 또는 호출자가 호출 체인 추가로 위임 수 있습니다.  브라우저 스크립트 엔진 내 경우를 예를 들어, 하는 `InvokeEx` 호출을 외부 개체, 개체를 따를 수는 `pspCaller` 체인 스크립트 엔진 또는 브라우저에서 서비스를 가져오는 데.  \(호출 체인 만들기 체인 동일 아닙니다\-컨테이너 체인 또는 체인 사이트 라고도 합니다.  만들기 체인 같은 일부 다른 메커니즘을 통해 사용할 수 있습니다 `IObjectWithSite`.\)|  
|`this`포인터|DISPATCH\_METHOD 설정 된 경우 `wFlags`, "this"이 값에 대 한 "명명 된 매개" 있을 수 있습니다.  DISPID는 DISPID\_THIS 되어 그 첫 번째 명명 된 매개 변수 여야 합니다.|  
  
 사용 되지 않은 `riid` 매개 변수에서 `IDispatch::Invoke` 제거 되었습니다.  
  
 `puArgArr` 매개 변수에서 `IDispatch::Invoke` 제거 되었습니다.  
  
 참조는 `IDispatch::Invoke` 설명서에 대 한 다음 예제:  
  
 "인수를 사용 하 여 메서드를 호출"  
  
 "속성 가져오기 및 설정"  
  
 "매개 변수 전달"  
  
 "인덱싱된 속성"  
  
 "호출 하는 동안 예외 발생"  
  
 "오류 반환"  
  
## 반환 값  
 다음 값 중 하나를 반환합니다.  
  
|||  
|-|-|  
|`S_OK`|성공|  
|DISP\_E\_BADPARAMCOUNT|DISPPARAMS에 제공 된 요소 수가 메서드 또는 속성에서 허용 하는 인수의 개수와 다릅니다.|  
|DISP\_E\_BADVARTYPE|인수 중 하나가 `rgvarg` 잘못 된 variant 형식입니다.|  
|DISP\_E\_EXCEPTION|응용 프로그램 예외를 발생 시킬 필요가 없습니다.  이 경우에 구조를 전달 `pei` 필수.|  
|DISP\_E\_MEMBERNOTFOUND|요청한 구성원이 존재 하지 않는 또는 호출을 `InvokeEx` 는 읽기 전용 속성의 값을 설정 하 려 했습니다.|  
|DISP\_E\_NONAMEDARGS|이 구현의 `IDispatch` 명명 된 인수를 지원 하지 않습니다.|  
|DISP\_E\_OVERFLOW|인수 중 하나가 `rgvarg` 지정 된 형식으로 강제 변환할 수 없습니다.|  
|DISP\_E\_PARAMNOTFOUND|Dispid 매개 변수 중 하나에 메서드 매개 변수에 일치 하지 않습니다.|  
|DISP\_E\_TYPEMISMATCH|하나 이상의 인수를 강제할 수 없습니다.|  
|DISP\_E\_UNKNOWNLCID|문자열 인수는 LCID에 따라 호출 되는 멤버를 해석 하 고 LCID가 인식 되지 않습니다.  인수를 해석하는 데 LCID가 필요하지 않은 경우, 이 오류는 반환되지 않을 것입니다.|  
|DISP\_E\_PARAMNOTOPTIONAL|필수 매개 변수를 생략했습니다.|  
  
## 예제  
  
```  
VARIANT var;  
   BSTR bstrName;  
   DISPID dispid;  
   IDispatchEx *pdex;  
   DISPPARAMS dispparamsNoArgs = {NULL, NULL, 0, 0};  
  
   // Assign to pdex and bstrName  
   if (SUCCEEDED(pdex->GetDispID(bstrName, fdexNameCaseSensitive, &dispid)))  
   {  
      pdex->InvokeEx(dispid, LOCALE_USER_DEFAULT,  
         DISPATCH_PROPERTYGET, &dispparamsNoArgs,   
         &var, NULL, NULL);  
   }  
```  
  
## 참고 항목  
 [IDispatchEx 인터페이스](../../winscript/reference/idispatchex-interface.md)   
 [IDispatchEx::GetDispID](../../winscript/reference/idispatchex-getdispid.md)   
 [IDispatchEx::GetNextDispID](../../winscript/reference/idispatchex-getnextdispid.md)