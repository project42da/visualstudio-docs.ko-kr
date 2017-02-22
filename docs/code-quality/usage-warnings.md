---
title: "사용법 경고 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.codeanalysis.usagerules"
helpviewer_keywords: 
  - "경고, 사용법"
  - "관리 코드 분석 경고, 사용법 경고"
  - "사용법 경고"
ms.assetid: fe7dc2a3-289d-4bf7-a1e4-0947a81287c4
caps.latest.revision: 24
caps.handback.revision: 24
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 사용법 경고
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

사용법 경고는 .NET Framework를 제대로 사용하도록 지원합니다.  
  
## 단원 내용  
  
|규칙|설명|  
|--------|--------|  
|[CA1801: 사용되지 않은 매개 변수를 검토하십시오.](../Topic/CA1801:%20Review%20unused%20parameters.md)|메서드 시그니처에 메서드 본문에서 사용되지 않는 매개 변수가 있습니다.|  
|[CA1806: 메서드 결과를 무시하지 마십시오.](../code-quality/ca1806-do-not-ignore-method-results.md)|새 개체가 만들어지지만 사용되지 않거나, 새 문자열을 만들고 반환하는 메서드가 호출되고 새 문자열이 사용되지 않거나, COM 또는 P\/Invoke 메서드가 사용되지 않는 오류 코드나 HRESULT를 반환합니다.|  
|[CA1816: GC.SuppressFinalize를 올바르게 호출하십시오.](../code-quality/ca1816-call-gc-suppressfinalize-correctly.md)|Dispose 구현인 메서드가 GC.SuppressFinalize를 호출하지 않거나, Dispose 구현이 아닌 메서드가 GC.SuppressFinalize를 호출하거나, 메서드가 GC.SuppressFinalize를 호출하고 this\(Visual Basic의 경우 Me\) 이외의 값을 전달합니다.|  
|[CA2200: 스택 정보를 유지하도록 다시 throw하십시오.](../code-quality/ca2200-rethrow-to-preserve-stack-details.md)|예외가 다시 throw되며 예외가 throw 문에 명시적으로 지정되어 있습니다.  throw 문에 예외를 지정하여 예외가 다시 throw되면 예외를 throw한 원래 메서드와 현재 메서드 간의 메서드 호출 목록이 손실됩니다.|  
|[CA2201: 예약된 예외 형식을 발생시키지 마십시오.](../code-quality/ca2201-do-not-raise-reserved-exception-types.md)|따라서 원래 오류를 감지하고 디버깅하기 어렵게 됩니다.|  
|[CA2202: 개체를 여러 번 삭제하지 마십시오.](../code-quality/ca2202-do-not-dispose-objects-multiple-times.md)|같은 개체에 대해 System.IDisposable.Dispose 또는 Dispose와 동일한 기능의 메서드\(예를 들어, 일부 형식의 Close\(\) 메서드\)가 여러 번 호출될 수 있는 코드 경로가 메서드 구현에 포함되어 있습니다.|  
|[CA2204: 리터럴의 철자가 맞아야 합니다.](../code-quality/ca2204-literals-should-be-spelled-correctly.md)|메서드 본문의 리터럴 문자열에 Microsoft 맞춤법 검사 라이브러리에서 인식하지 못하는 단어가 하나 이상 있습니다.|  
|[CA2205: Win32 API에 있는 동일한 기능의 관리되는 항목을 사용하십시오.](../code-quality/ca2205-use-managed-equivalents-of-win32-api.md)|플랫폼 호출 메서드가 정의되었고 이와 동일한 기능을 수행하는 메서드가 .NET Framework 클래스 라이브러리에 있습니다.|  
|[CA2207: 값 형식 정적 필드를 인라인으로 초기화하십시오.](../code-quality/ca2207-initialize-value-type-static-fields-inline.md)|값 형식에서 명시적인 정적 생성자를 선언합니다.  이 규칙 위반 문제를 해결하려면 모든 정적 데이터를 선언할 때 초기화하고 정적 생성자를 제거합니다.|  
|[CA2208: 인수 예외를 올바르게 인스턴스화하십시오.](../code-quality/ca2208-instantiate-argument-exceptions-correctly.md)|ArgumentException 또는 ArgumentException에서 파생된 예외 형식의 기본\(매개 변수가 없는\) 생성자를 호출했거나, ArgumentException 또는 ArgumentException에서 파생된 예외 형식의 매개 변수가 있는 생성자에 잘못된 문자열 인수가 전달되었습니다.|  
|[CA2211: 비상수 필드는 노출되면 안 됩니다.](../code-quality/ca2211-non-constant-fields-should-not-be-visible.md)|상수도 아니고 읽기 전용도 아닌 static 필드는 스레드로부터 안전하지 않습니다.  이러한 필드에 대한 액세스는 신중하게 제어해야 하며 클래스 개체에 대한 액세스를 동기화하는 고급 프로그래밍 기술을 필요로 합니다.|  
|[CA2212: 서비스 구성 요소를 WebMethod를 사용하여 표시하지 마십시오.](../code-quality/ca2212-do-not-mark-serviced-components-with-webmethod.md)|System.EnterpriseServices.ServicedComponent로부터 상속하는 형식의 메서드가 System.Web.Services.WebMethodAttribute로 표시되어 있습니다.  WebMethodAttribute 및 ServicedComponent 메서드에는 컨텍스트와 트랜잭션 흐름에 있어 충돌하는 동작 및 요구 사항이 있으므로 메서드의 동작이 일부 시나리오에서 잘못됩니다.|  
|[CA2213: 삭제 가능한 필드는 삭제해야 합니다.](../code-quality/ca2213-disposable-fields-should-be-disposed.md)|System.IDisposable을 구현하는 형식이 마찬가지로 IDisposable을 구현하는 형식으로 된 필드를 선언합니다.  필드의 Dispose 메서드가 선언 형식의 Dispose 메서드에 의해 호출되지 않습니다.|  
|[CA2214: 재정의 가능한 메서드를 생성자에서 호출하지 마십시오.](../Topic/CA2214:%20Do%20not%20call%20overridable%20methods%20in%20constructors.md)|생성자가 가상 메서드를 호출할 때 이 메서드를 호출하는 인스턴스의 생성자가 실행되지 않았을 가능성이 있습니다.|  
|[CA2215: Dispose 메서드는 기본 클래스 Dispose를 호출해야 합니다.](../code-quality/ca2215-dispose-methods-should-call-base-class-dispose.md)|삭제 가능한 형식으로부터 상속하는 형식은 자신의 Dispose 메서드에서 기본 형식의 Dispose 메서드를 호출해야 합니다.|  
|[CA2216: 삭제 가능한 형식은 종료자를 선언해야 합니다.](../code-quality/ca2216-disposable-types-should-declare-finalizer.md)|System.IDisposable을 구현하고, 관리되지 않는 리소스의 사용을 암시하는 필드를 포함하는 형식이 Object.Finalize에 설명된 대로 종료자를 구현하지 않습니다.|  
|[CA2217: 열거형을 FlagsAttribute로 표시하지 마십시오.](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)|외부에서 볼 수 있는 열거형이 FlagsAttribute로 표시되어 있고, 2의 거듭제곱 또는 열거형에 정의된 다른 값의 조합이 아닌 값이 하나 이상 들어 있습니다.|  
|[CA2218: Equals를 재정의할 때 GetHashCode를 재정의하십시오.](../code-quality/ca2218-override-gethashcode-on-overriding-equals.md)|GetHashCode는 현재 인스턴스를 기반으로 해싱 알고리즘 및 해시 테이블과 같은 데이터 구조체에 적합한 값을 반환합니다.  형식이 같은 동일한 두 개체는 동일한 해시 코드를 반환해야 합니다.|  
|[CA2219: exception 절에서 예외를 발생시키지 마십시오.](../Topic/CA2219:%20Do%20not%20raise%20exceptions%20in%20exception%20clauses.md)|finally 또는 fault 절에서 예외가 발생하는 경우 새 예외가 활성 예외를 숨깁니다.  filter 절에서 예외가 발생하는 경우 런타임이 자동으로 예외를 catch합니다.  따라서 원래 오류를 감지하고 디버깅하기 어렵게 됩니다.|  
|[CA2220: 종료자는 기본 클래스 종료자를 호출해야 합니다.](../code-quality/ca2220-finalizers-should-call-base-class-finalizer.md)|종료는 상속 계층을 통해 전파되어야 합니다.  이를 위해 형식은 자체 Finalize 메서드에서 기본 클래스의 Finalize 메서드를 호출해야 합니다.|  
|[CA2221: 종료자는 protected여야 합니다.](../code-quality/ca2221-finalizers-should-be-protected.md)|종료자에서는 패밀리 액세스 한정자를 사용해야 합니다.|  
|[CA2222: 상속된 멤버 노출 수준을 낮추지 마십시오.](../code-quality/ca2222-do-not-decrease-inherited-member-visibility.md)|상속된 멤버에 대한 액세스 한정자는 변경하면 안 됩니다.  상속된 멤버를 private으로 변경하더라도 호출자가 메서드의 기본 클래스 구현에 액세스하는 것을 막을 수 없습니다.|  
|[CA2223: 멤버는 반환 형식 이외의 것도 달라야 합니다.](../Topic/CA2223:%20Members%20should%20differ%20by%20more%20than%20return%20type.md)|공용 언어 런타임에서는 반환 값만 다르고 다른 면에서는 동일한 멤버를 구분할 수 있지만 이 기능은 공용 언어 사양에 해당되지 않으며 .NET 프로그래밍 언어의 공통 기능이 아닙니다.|  
|[CA2224: 같음 연산자를 오버로드할 때 Equals를 재정의하십시오.](../code-quality/ca2224-override-equals-on-overloading-operator-equals.md)|public 형식이 같음 연산자를 구현하지만 Object.Equals를 재정의하지 않습니다.|  
|[CA2225: 연산자 오버로드에는 명명된 대체 항목이 있습니다.](../Topic/CA2225:%20Operator%20overloads%20have%20named%20alternates.md)|연산자 오버로드가 감지되었으며 예상되는 이름의 대체 메서드를 찾을 수 없습니다.  명명된 대체 멤버는 해당 연산자와 동일한 기능에 액세스할 수 있도록 해주며, 오버로드된 연산자가 지원되지 않는 언어로 프로그래밍하는 개발자에게 제공됩니다.|  
|[CA2226: 연산자에는 대칭 오버로드가 있어야 합니다.](../code-quality/ca2226-operators-should-have-symmetrical-overloads.md)|형식이 같음 연산자 또는 같지 않음 연산자를 구현하면서 그 반대 연산자를 구현하지 않습니다.|  
|[CA2227: 컬렉션 속성은 읽기 전용이어야 합니다.](../code-quality/ca2227-collection-properties-should-be-read-only.md)|쓰기 가능한 컬렉션 속성을 통해 사용자는 컬렉션을 다른 컬렉션으로 바꿀 수 있습니다.  읽기 전용 속성은 컬렉션을 바꾸지 못하도록 하지만 개별 멤버를 설정하는 것은 여전히 가능합니다.|  
|[CA2228: 릴리스되지 않은 리소스 형식을 제공하지 마십시오.](../Topic/CA2228:%20Do%20not%20ship%20unreleased%20resource%20formats.md)|.NET Framework 시험판 버전을 사용하여 빌드된 리소스 파일은 지원되는 .NET Framework 버전에서 사용하지 못할 수 있습니다.|  
|[CA2229: serialization 생성자를 구현하십시오.](../code-quality/ca2229-implement-serialization-constructors.md)|이 규칙 위반 문제를 해결하려면 serialization 생성자를 구현합니다.  봉인 클래스의 경우에는 생성자를 private으로 만들고, 그 밖의 경우에는 protected로 만듭니다.|  
|[CA2230: 가변 인수로 params를 사용하십시오.](../code-quality/ca2230-use-params-for-variable-arguments.md)|public 또는 protected 형식에 params 키워드 대신 VarArgs 호출 규칙을 사용하는 public 또는 protected 메서드가 들어 있습니다.|  
|[CA2231: ValueType.Equals를 재정의할 때 같음 연산자를 오버로드하십시오.](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)|값 형식이 Object.Equals를 재정의하지만 같음 연산자를 구현하지 않습니다.|  
|[CA2232: Windows Forms 진입점을 STAThread를 사용하여 표시하십시오.](../code-quality/ca2232-mark-windows-forms-entry-points-with-stathread.md)|STAThreadAttribute는 응용 프로그램에 대한 COM 스레딩 모델이 단일 스레드 아파트임을 나타냅니다.  이 특성은 Windows Forms을 사용하는 응용 프로그램의 진입점에 있어야 합니다. 이 특성을 생략하면 Windows 구성 요소가 제대로 작동하지 않을 수 있습니다.|  
|[CA2233: 연산은 오버플로되지 않아야 합니다.](../code-quality/ca2233-operations-should-not-overflow.md)|산술 연산을 수행하려면 먼저 피연산자의 유효성을 검사하여 연산의 결과가 관련 데이터 형식의 가능한 값 범위를 벗어나지 않도록 해야 합니다.|  
|[CA2234: 문자열 대신 System.Uri 개체를 전달하십시오.](../Topic/CA2234:%20Pass%20System.Uri%20objects%20instead%20of%20strings.md)|이름에 "uri", "URI", "urn", "URN", "url" 또는 "URL"이 포함된 문자열 매개 변수가 있는 메서드가 호출되었습니다.  메서드의 선언 형식에 System.Uri 매개 변수를 가진 해당 메서드 오버로드가 들어 있습니다.|  
|[CA2235: 모두 serialize할 수 없는 필드로 표시하십시오.](../code-quality/ca2235-mark-all-non-serializable-fields.md)|serialize할 수 없는 형식의 인스턴스 필드가 serialize할 수 있는 형식에 정의되었습니다.|  
|[CA2236: ISerializable 형식에서 기본 클래스 메서드를 호출하십시오.](../code-quality/ca2236-call-base-class-methods-on-iserializable-types.md)|이 규칙 위반 문제를 해결하려면 해당하는 파생된 형식의 메서드나 생성자에서 기본 형식 GetObjectData 메서드나 serialization 생성자를 호출합니다.|  
|[CA2237: ISerializable 형식을 SerializableAttribute로 표시하십시오.](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)|공용 언어 런타임에서 serializable로 인식되도록 하려면 형식이 ISerializable 인터페이스 구현을 통해 사용자 지정 serialization 루틴을 사용하는 경우에도 형식을 SerializableAttribute 특성으로 표시해야 합니다.|  
|[CA2238: serialization 메서드를 올바르게 구현하십시오.](../code-quality/ca2238-implement-serialization-methods-correctly.md)|serialization 이벤트를 처리하는 메서드에 올바른 시그너처, 반환 형식 또는 노출 수준이 없습니다.|  
|[CA2239: 선택적 필드에 deserialization 메서드를 제공하십시오.](../code-quality/ca2239-provide-deserialization-methods-for-optional-fields.md)|형식에 System.Runtime.Serialization.OptionalFieldAttribute 특성으로 표시된 필드가 있으며 형식에서 deserialization 이벤트 처리 메서드를 제공하지 않습니다.|  
|[CA2240: ISerializable을 올바르게 구현하십시오.](../Topic/CA2240:%20Implement%20ISerializable%20correctly.md)|이 규칙 위반 문제를 해결하려면 GetObjectData 메서드를 표시하고 재정의 가능하도록 만든 다음 모든 인스턴스 필드가 serialization 프로세스에 포함되었는지 또는 NonSerializedAttribute 특성으로 명시적으로 표시되었는지 확인합니다.|  
|[CA2241: 형식 메서드에 올바른 인수를 제공하십시오.](../code-quality/ca2241-provide-correct-arguments-to-formatting-methods.md)|System.String.Format에 전달된 format 인수에 각 개체 인수에 해당하는 형식 항목이 없거나 각 형식 항목에 해당하는 개체 인수가 없습니다.|  
|[CA2242: NaN에 대해 정확하게 테스트하십시오.](../code-quality/ca2242-test-for-nan-correctly.md)|이 식은 Single.Nan 또는 Double.Nan에 대해 값을 테스트합니다.  값을 테스트하려면 Single.IsNan\(Single\) 또는 Double.IsNan\(Double\)을 사용합니다.|  
|[CA2243: 특성 문자열 리터럴이 올바르게 구문 분석되어야 합니다.](../code-quality/ca2243-attribute-string-literals-should-parse-correctly.md)|특성의 문자열 리터럴 매개 변수가 URL, GUID 또는 버전에 대해 구문을 올바르게 분석하지 않습니다.|