---
title: "관리 코드에 대한 보안 규칙 규칙 집합 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 564aeac6-03fa-41b0-b655-88179f0ab01b
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 9
---
# 관리 코드에 대한 보안 규칙 규칙 집합
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

보고되는 잠재적 보안 문제의 수를 최대화하려면 Microsoft 보안 규칙이라는 규칙 집합을 포함해야 합니다.  
  
|규칙|설명|  
|--------|--------|  
|[CA2100](../code-quality/ca2100-review-sql-queries-for-security-vulnerabilities.md)|보안상 취약한 부분이 있는지 SQL 쿼리를 검토하십시오.|  
|[CA2102](../code-quality/ca2102-catch-non-clscompliant-exceptions-in-general-handlers.md)|일반 처리기에서 비 CLSCompliant 예외를 catch하십시오.|  
|[CA2103](../code-quality/ca2103-review-imperative-security.md)|CA2103: 명령적 보안을 검토하십시오.|  
|[CA2104](../code-quality/ca2104-do-not-declare-read-only-mutable-reference-types.md)|변경 가능한 읽기 전용 참조 형식을 선언하지 마십시오.|  
|[CA2105](../code-quality/ca2105-array-fields-should-not-be-read-only.md)|배열 필드는 읽기 전용이면 안 됩니다.|  
|[CA2106](../code-quality/ca2106-secure-asserts.md)|어설션을 안전하게 하십시오.|  
|[CA2107](../code-quality/ca2107-review-deny-and-permit-only-usage.md)|CA2107: Deny 및 PermitOnly 사용을 검토하십시오.|  
|[CA2108](../code-quality/ca2108-review-declarative-security-on-value-types.md)|값 형식에서 선언적 보안을 검토하십시오.|  
|[CA2109](../code-quality/ca2109-review-visible-event-handlers.md)|CA2109: 표시되는 이벤트 처리기를 검토하십시오.|  
|[CA2111](../code-quality/ca2111-pointers-should-not-be-visible.md)|포인터는 노출되면 안 됩니다.|  
|[CA2112](../code-quality/ca2112-secured-types-should-not-expose-fields.md)|보안 형식은 필드를 노출하면 안 됩니다.|  
|[CA2114](../code-quality/ca2114-method-security-should-be-a-superset-of-type.md)|메서드 보안은 형식의 상위 집합이어야 합니다.|  
|[CA2115](../Topic/CA2115:%20Call%20GC.KeepAlive%20when%20using%20native%20resources.md)|네이티브 리소스를 사용하는 경우에는 GC.KeepAlive를 호출하십시오.|  
|[CA2116](../Topic/CA2116:%20APTCA%20methods%20should%20only%20call%20APTCA%20methods.md)|APTCA 메서드는 APTCA 메서드만 호출해야 합니다.|  
|[CA2117](../code-quality/ca2117-aptca-types-should-only-extend-aptca-base-types.md)|APTCA 형식은 APTCA 기본 형식만 확장해야 합니다.|  
|[CA2118](../code-quality/ca2118-review-suppressunmanagedcodesecurityattribute-usage.md)|CA2118: SuppressUnmanagedCodeSecurityAttribute 사용을 검토하십시오.|  
|[CA2119](../code-quality/ca2119-seal-methods-that-satisfy-private-interfaces.md)|private 인터페이스를 만족하는 메서드를 봉인하십시오.|  
|[CA2120](../Topic/CA2120:%20Secure%20serialization%20constructors.md)|serialization 생성자를 안전하게 하십시오.|  
|[CA2121](../Topic/CA2121:%20Static%20constructors%20should%20be%20private.md)|static 생성자는 private이어야 합니다.|  
|[CA2122](../code-quality/ca2122-do-not-indirectly-expose-methods-with-link-demands.md)|링크 요청이 있는 메서드를 간접적으로 노출하지 마십시오.|  
|[CA2123](../code-quality/ca2123-override-link-demands-should-be-identical-to-base.md)|재정의 링크 요청은 기본 형식의 링크 요청과 같아야 합니다.|  
|[CA2124](../code-quality/ca2124-wrap-vulnerable-finally-clauses-in-outer-try.md)|취약한 finally 절을 외부 try에 래핑하십시오.|  
|[CA2126](../Topic/CA2126:%20Type%20link%20demands%20require%20inheritance%20demands.md)|형식 링크 요청에는 상속 요청이 필요합니다.|  
|[CA2130](../code-quality/ca2130-security-critical-constants-should-be-transparent.md)|보안 위험 상수는 투명해야 합니다.|  
|[CA2131](../code-quality/ca2131-security-critical-types-may-not-participate-in-type-equivalence.md)|보안에 중요한 형식은 형식 등가에 참여할 수 없습니다.|  
|[CA2132](../code-quality/ca2132-default-constructors-must-be-at-least-as-critical-as-base-type-default-constructors.md)|기본 생성자는 기본 형식의 기본 생성자 이상으로 중요해야 합니다.|  
|[CA2133](../code-quality/ca2133-delegates-must-bind-to-methods-with-consistent-transparency.md)|대리인은 투명도가 일관된 메서드에 바인딩해야 합니다.|  
|[CA2134](../code-quality/ca2134-methods-must-keep-consistent-transparency-when-overriding-base-methods.md)|메서드는 기본 메서드를 재정의할 때 일관성 있는 방식을 유지해야 합니다.|  
|[CA2135](../Topic/CA2135:%20Level%202%20assemblies%20should%20not%20contain%20LinkDemands.md)|수준 2 어셈블리는 LinkDemands를 포함해서는 안 됩니다.|  
|[CA2136](../Topic/CA2136:%20Members%20should%20not%20have%20conflicting%20transparency%20annotations.md)|멤버는 충돌하는 투명도 주석을 가져서는 안 됩니다.|  
|[CA2137](../Topic/CA2137:%20Transparent%20methods%20must%20contain%20only%20verifiable%20IL.md)|투명한 메서드는 안정형 IL만 포함해야 합니다.|  
|[CA2138](../code-quality/ca2138-transparent-methods-must-not-call-methods-with-the-suppressunmanagedcodesecurity-attribute.md)|투명한 메서드는 SuppressUnmanagedCodeSecurity 특성을 가진 메서드를 호출해서는 안 됩니다.|  
|[CA2139](../Topic/CA2139:%20Transparent%20methods%20may%20not%20use%20the%20HandleProcessCorruptingExceptions%20attribute.md)|투명한 메서드는 HandleProcessCorruptingExceptions 특성을 사용할 수 없습니다.|  
|[CA2140](../code-quality/ca2140-transparent-code-must-not-reference-security-critical-items.md)|투명 코드는 보안에 중요한 항목을 참조해서는 안 됩니다.|  
|[CA2141](../code-quality/ca2141-transparent-methods-must-not-satisfy-linkdemands.md)|투명한 메서드는 LinkDemands를 충족해서는 안 됩니다|  
|[CA2142](../code-quality/ca2142-transparent-code-should-not-be-protected-with-linkdemands.md)|투명한 코드는 LinkDemands를 사용하여 보호해서는 안 됩니다.|  
|[CA2143](../Topic/CA2143:%20Transparent%20methods%20should%20not%20use%20security%20demands.md)|투명한 메서드는 보안 요청을 사용해서는 안 됩니다.|  
|[CA2144](../code-quality/ca2144-transparent-code-should-not-load-assemblies-from-byte-arrays.md)|투명 코드는 바이트 배열에서 어셈블리를 로드해서는 안 됩니다.|  
|[CA2145](../code-quality/ca2145-transparent-methods-should-not-be-decorated-with-the-suppressunmanagedcodesecurityattribute.md)|투명한 메서드는 SuppressUnmanagedCodeSecurityAttribute로 데코레이팅해서는 안 됩니다.|  
|[CA2146](../code-quality/ca2146-types-must-be-at-least-as-critical-as-their-base-types-and-interfaces.md)|형식은 기본 형식 및 인터페이스 이상으로 중요해야 합니다.|  
|[CA2147](../code-quality/ca2147-transparent-methods-may-not-use-security-asserts.md)|투명 메서드는 보안 어설션을 사용할 수 없습니다.|  
|[CA2149](../code-quality/ca2149-transparent-methods-must-not-call-into-native-code.md)|투명한 메서드는 네이티브 코드를 호출해서는 안 됩니다.|  
|[CA2210](../Topic/CA2210:%20Assemblies%20should%20have%20valid%20strong%20names.md)|CA2210: 어셈블리에는 올바른 강력한 이름을 사용해야 합니다.|