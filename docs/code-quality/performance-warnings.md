---
title: "성능 경고 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.codeanalysis.performancerules"
helpviewer_keywords: 
  - "경고, 성능"
  - "성능 경고"
  - "성능, 경고"
  - "관리 코드 분석 경고, 성능 경고"
ms.assetid: e014ac3a-02e6-46d9-942c-3491dd63782f
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 22
---
# 성능 경고
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

성능 경고는 고성능 라이브러리 및 응용 프로그램을 지원합니다.  
  
## 단원 내용  
  
|규칙|설명|  
|--------|--------|  
|[CA1800: 불필요하게 캐스팅하지 마십시오.](../code-quality/ca1800-do-not-cast-unnecessarily.md)|중복 캐스팅을 수행하면 성능이 저하됩니다. 특히 간단한 반복 문에서 캐스팅이 수행될 때 더욱 그러합니다.|  
|[CA1801: 사용되지 않은 매개 변수를 검토하십시오.](../Topic/CA1801:%20Review%20unused%20parameters.md)|메서드 시그니처에 메서드 본문에서 사용되지 않는 매개 변수가 있습니다.|  
|[CA1802: 가능하면 리터럴을 사용하십시오.](../code-quality/ca1802-use-literals-where-appropriate.md)|필드가 static 및 read\-only\([!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]의 경우 Shared 및 ReadOnly\)로 선언되었으며 컴파일 타임에 계산할 수 있는 값으로 초기화됩니다.  대상으로 지정된 필드에 할당되는 값을 컴파일 타임에 계산할 수 있으므로 값이 런타임이 아닌 컴파일 시 계산되도록 선언을 const\([!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]의 경우 Const\) 필드로 변경합니다.|  
|[CA1804: 사용되지 않는 로컬 항목을 제거하십시오.](../code-quality/ca1804-remove-unused-locals.md)|사용되지 않는 지역 변수와 불필요한 할당으로 어셈블리의 크기가 증가하고 성능이 저하될 수 있습니다.|  
|[CA1806: 메서드 결과를 무시하지 마십시오.](../code-quality/ca1806-do-not-ignore-method-results.md)|새 개체가 만들어지지만 사용되지 않거나, 새 문자열을 만들고 반환하는 메서드가 호출되었는데 새 문자열이 사용되지 않거나, COM\(구성 요소 개체 모델\) 또는 P\/Invoke 메서드가 사용되지 않는 오류 코드나 HRESULT를 반환합니다.|  
|[CA1809: 불필요한 로컬 항목을 사용하지 마십시오.](../code-quality/ca1809-avoid-excessive-locals.md)|값을 메모리가 아닌 프로세서 레지스터에 저장하는 방법은 성능 최적화에 많이 사용되는 방법이며 "값의 레지스터 등록"이라고도 합니다.  모든 지역 변수가 레지스터에 등록될 수 있는 가능성을 높이려면 지역 변수의 개수를 64개로 제한합니다.|  
|[CA1810: 참조 형식 정적 필드를 인라인으로 초기화하십시오.](../code-quality/ca1810-initialize-reference-type-static-fields-inline.md)|형식이 명시적인 정적 생성자를 선언하면 JIT\(Just\-in\-Time\) 컴파일러는 형식의 각 정적 메서드와 인스턴스 생성자에 검사를 추가하여 정적 생성자를 이전에 호출했는지 확인합니다.  정적 생성자 검사로 인해 성능이 저하될 수 있습니다.|  
|[CA1811: 호출되지 않는 전용 코드를 사용하지 마십시오.](../code-quality/ca1811-avoid-uncalled-private-code.md)|어셈블리에 전용 또는 내부\(어셈블리 수준\) 멤버의 호출자가 없고, 공용 언어 런타임에서도 이 멤버를 호출하지 않으며, 대리자에서도 이 멤버를 호출하지 않습니다.|  
|[CA1812: 인스턴스화되지 않은 내부 클래스를 사용하지 마십시오.](../Topic/CA1812:%20Avoid%20uninstantiated%20internal%20classes.md)|어셈블리 수준 형식의 인스턴스가 어셈블리에서 코드에 의해 만들어지지 않습니다.|  
|[CA1813: 봉인되지 않은 특성을 사용하지 마십시오.](../code-quality/ca1813-avoid-unsealed-attributes.md)|[!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 클래스 라이브러리는 사용자 지정 특성을 검색하는 메서드를 제공합니다.  기본적으로 이러한 메서드는 특성 상속 계층을 검색합니다.  특성을 봉인하면 상속 계층을 검색하지 않으므로 성능이 향상될 수 있습니다.|  
|[CA1814: 다차원 배열보다 가변 배열을 사용하십시오.](../code-quality/ca1814-prefer-jagged-arrays-over-multidimensional.md)|가변 배열의 요소에는 배열이 사용됩니다.  요소를 구성하는 배열의 크기는 서로 다를 수 있습니다. 이 경우 일부 데이터 집합을 위한 공간을 절약할 수 있습니다.|  
|[CA1815: 값 형식에서 Equals 또는 같음 연산자를 재정의하십시오.](../Topic/CA1815:%20Override%20equals%20and%20operator%20equals%20on%20value%20types.md)|값 형식의 경우 Equals의 상속된 구현에서 Reflection 라이브러리를 사용하며 모든 필드의 내용을 비교합니다.  Reflection에는 많은 계산이 요구되며 모든 필드의 일치 여부를 비교하는 것이 불필요할 수 있습니다.  사용자가 인스턴스를 비교 또는 정렬하거나 인스턴스를 해시 테이블 키로 사용할 것으로 예측되는 경우에는 값 형식에서 Equals를 구현해야 합니다.|  
|[CA1816: GC.SuppressFinalize를 올바르게 호출하십시오.](../code-quality/ca1816-call-gc-suppressfinalize-correctly.md)|Dispose 구현인 메서드가 GC.SuppressFinalize를 호출하지 않거나, Dispose 구현이 아닌 메서드가 GC.SuppressFinalize를 호출하거나, 메서드가 GC.SuppressFinalize를 호출하고 this\([!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]의 경우 Me\) 이외의 값을 전달합니다.|  
|[CA1819: 속성은 배열을 반환해서는 안 됩니다.](../code-quality/ca1819-properties-should-not-return-arrays.md)|속성에서 반환된 배열은 속성이 읽기 전용이어도 쓰기 금지되지 않습니다.  배열을 무단으로 변경하지 못하도록 하려면 속성에서 배열의 복사본을 반환해야 합니다.  일반적으로 사용자는 이러한 속성을 호출할 경우 성능에 부정적인 영향을 준다는 것을 인식하지 못합니다.|  
|[CA1820: 문자열 길이를 사용하여 문자열이 비었는지 테스트하십시오.](../code-quality/ca1820-test-for-empty-strings-using-string-length.md)|String.Length 속성이나 String.IsNullOrEmpty 메서드를 사용하여 문자열을 비교하는 것이 Equals를 사용하는 것보다 훨씬 더 빠릅니다.|  
|[CA1821: 빈 종료자를 제거하십시오.](../code-quality/ca1821-remove-empty-finalizers.md)|개체 수명을 추적할 때에는 추가로 성능 오버헤드가 발생하므로 가능한 경우 종료자를 사용하지 마십시오.  빈 종료자는 아무런 장점 없이 오버헤드만 가중시킵니다.|  
|[CA1822: 멤버를 static으로 표시하십시오.](../Topic/CA1822:%20Mark%20members%20as%20static.md)|인스턴스 데이터에 액세스하지 않거나 인스턴스 메서드를 호출하지 않는 멤버는 static\([!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]의 경우 Shared\)으로 표시할 수 있습니다.  메서드를 static으로 표시하면 컴파일러는 이러한 멤버에 대한 비가상 호출 사이트를 내보냅니다.  이 경우 성능이 중요한 코드에서 성능이 크게 향상될 수 있습니다.|  
|[CA1823: 사용되지 않는 전용 필드를 사용하지 마십시오.](../code-quality/ca1823-avoid-unused-private-fields.md)|어셈블리에서 액세스되지 않는 것으로 보이는 전용 필드가 발견되었습니다.|  
|[CA1824: NeutralResourcesLanguageAttribute로 어셈블리 표시](../Topic/CA1824:%20Mark%20assemblies%20with%20NeutralResourcesLanguageAttribute.md)|NeutralResourcesLanguage 특성을 사용하여 어셈블리에 대한 중립 문화권의 리소스를 표시하는 데 사용된 언어를 ResourceManager에 알릴 수 있습니다.  이렇게 하면 로드한 첫 리소스에 대한 찾기 성능을 향상시킬 수 있으며 작업이 간단해집니다.|