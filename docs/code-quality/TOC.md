# [코드 분석 도구를 사용하여 응용 프로그램 품질 분석](analyzing-application-quality-by-using-code-analysis-tools.md)
## [코드 분석을 사용하여 관리 코드 품질 분석](analyzing-managed-code-quality-by-using-code-analysis.md)
### [관리 코드에 대한 코드 분석 개요](code-analysis-for-managed-code-overview.md)
### [방법: 관리 코드에 대한 자동 코드 분석 활성화 및 비활성화](how-to-enable-and-disable-automatic-code-analysis-for-managed-code.md)
### [방법: 관리 코드에 대한 전체 솔루션 분석 활성화 및 비활성화](how-to-enable-and-disable-full-solution-analysis-for-managed-code.md)
### [자동 기능 일시 중단](automatic-feature-suspension.md)
### [방법: 관리 코드에 대해 수동으로 코드 분석 실행](how-to-run-code-analysis-manually-for-managed-code.md)
### [연습: 관리 코드의 코드 오류 분석](walkthrough-analyzing-managed-code-for-code-defects.md)
### [SuppressMessage 특성을 사용하여 경고 표시 안 함](suppress-warnings-by-using-the-suppressmessage-attribute.md)
#### [ISS(In Source Suppression) 개요](in-source-suppression-overview.md)
#### [방법: 메뉴 항목을 사용하여 경고 표시 안 함](how-to-suppress-warnings-by-using-the-menu-item.md)
### [방법: 생성된 코드에 대한 코드 분석 경고 표시 안 함](how-to-suppress-code-analysis-warnings-for-generated-code.md)
### [방법: 코드 분석 사전 사용자 지정](how-to-customize-the-code-analysis-dictionary.md)
### [무명 메서드 및 코드 분석](anonymous-methods-and-code-analysis.md)
### [방법: 관리 코드 오류 보기](how-to-view-managed-code-defects.md)
### [방법: 관리 코드 오류에 대한 작업 항목 만들기](how-to-create-a-work-item-for-a-managed-code-defect.md)
### [관리 코드 경고에 대한 코드 분석](code-analysis-for-managed-code-warnings.md)
#### [관리되는 코드에 대한 CheckId별 코드 분석 경고](code-analysis-warnings-for-managed-code-by-checkid.md)
#### [암호화 경고](cryptography-warnings.md)
##### [CA5350: 취약한 암호화 알고리즘 사용 안 함](ca5350-do-not-use-weak-cryptographic-algorithms.md)
##### [CA5351 끊어진 암호화 알고리즘을 사용하지 마십시오.](ca5351-do-not-use-broken-cryptographic-algorithms.md)
#### [디자인 경고](design-warnings.md)
##### [CA1000: 정적 멤버를 제네릭 형식으로 선언하지 마십시오.](ca1000-do-not-declare-static-members-on-generic-types.md)
##### [CA1001: 삭제 가능한 필드가 있는 형식은 삭제 가능해야 합니다.](ca1001-types-that-own-disposable-fields-should-be-disposable.md)
##### [CA1002: 제네릭 목록을 노출하지 마십시오.](ca1002-do-not-expose-generic-lists.md)
##### [CA1003: 제네릭 이벤트 처리기 인스턴스를 사용하십시오.](ca1003-use-generic-event-handler-instances.md)
##### [CA1004: 제네릭 메서드는 형식 매개 변수를 제공해야 합니다.](ca1004-generic-methods-should-provide-type-parameter.md)
##### [CA1005: 제네릭 형식에 매개 변수를 너무 많이 사용하지 마십시오.](ca1005-avoid-excessive-parameters-on-generic-types.md)
##### [CA1006: 멤버 시그니처에 제네릭 형식을 중첩하지 마십시오.](ca1006-do-not-nest-generic-types-in-member-signatures.md)
##### [CA1007: 적합한 제네릭을 사용하십시오.](ca1007-use-generics-where-appropriate.md)
##### [CA1008: 열거형에는&0; 값이 있어야 합니다.](ca1008-enums-should-have-zero-value.md)
##### [CA1009: 이벤트 처리기를 제대로 선언하십시오.](ca1009-declare-event-handlers-correctly.md)
##### [CA1010: 컬렉션은 제네릭 인터페이스를 구현해야 합니다.](ca1010-collections-should-implement-generic-interface.md)
##### [CA1011: 기본 형식을 매개 변수로 전달해 보십시오.](ca1011-consider-passing-base-types-as-parameters.md)
##### [CA1012: 추상 형식에는 생성자를 사용하면 안 됩니다.](ca1012-abstract-types-should-not-have-constructors.md)
##### [CA1013: 더하기 및 빼기를 오버로드할 때 같음 연산자를 오버로드하십시오.](ca1013-overload-operator-equals-on-overloading-add-and-subtract.md)
##### [CA1014: 어셈블리를 CLSCompliantAttribute로 표시하십시오.](ca1014-mark-assemblies-with-clscompliantattribute.md)
##### [CA1016: 어셈블리를 AssemblyVersionAttribute로 표시하십시오.](ca1016-mark-assemblies-with-assemblyversionattribute.md)
##### [CA1017: 어셈블리를 ComVisibleAttribute로 표시하십시오.](ca1017-mark-assemblies-with-comvisibleattribute.md)
##### [CA1018: 특성을 AttributeUsageAttribute로 표시하십시오.](ca1018-mark-attributes-with-attributeusageattribute.md)
##### [CA1019: 특성 인수의 접근자를 정의하십시오.](ca1019-define-accessors-for-attribute-arguments.md)
##### [CA1020: 형식이 부족한 네임스페이스를 사용하지 마십시오.](ca1020-avoid-namespaces-with-few-types.md)
##### [CA1021: out 매개 변수를 사용하지 마십시오.](ca1021-avoid-out-parameters.md)
##### [CA1023: 다차원 인덱서는 사용하지 마십시오.](ca1023-indexers-should-not-be-multidimensional.md)
##### [CA1024: 적합한 속성을 사용하십시오.](ca1024-use-properties-where-appropriate.md)
##### [CA1025: 반복 인수를 매개 변수 배열로 바꾸십시오.](ca1025-replace-repetitive-arguments-with-params-array.md)
##### [CA1026: 기본 매개 변수를 사용하면 안 됩니다.](ca1026-default-parameters-should-not-be-used.md)
##### [CA1027: 열거형을 FlagsAttribute로 표시하십시오.](ca1027-mark-enums-with-flagsattribute.md)
##### [CA1028: 열거형 저장소는 Int32여야 합니다.](ca1028-enum-storage-should-be-int32.md)
##### [CA1030: 적절한 경우 이벤트를 사용하십시오.](ca1030-use-events-where-appropriate.md)
##### [CA1031: 일반적인 예외 형식을 catch하지 마십시오.](ca1031-do-not-catch-general-exception-types.md)
##### [CA1032: 표준 예외 생성자를 구현하십시오.](ca1032-implement-standard-exception-constructors.md)
##### [CA1033: 인터페이스 메서드는 자식 형식에서 호출할 수 있어야 합니다.](ca1033-interface-methods-should-be-callable-by-child-types.md)
##### [CA1034: 중첩 형식은 노출하지 마십시오.](ca1034-nested-types-should-not-be-visible.md)
##### [CA1035: ICollection 구현에 강력한 형식의 멤버가 있습니다.](ca1035-icollection-implementations-have-strongly-typed-members.md)
##### [CA1036: 비교 가능한 형식에 메서드를 재정의하십시오.](ca1036-override-methods-on-comparable-types.md)
##### [CA1038: 열거자는 강력한 형식이어야 합니다.](ca1038-enumerators-should-be-strongly-typed.md)
##### [CA1039: 목록은 강력한 형식이어야 합니다.](ca1039-lists-are-strongly-typed.md)
##### [CA1040: 빈 인터페이스를 사용하지 마십시오.](ca1040-avoid-empty-interfaces.md)
##### [CA1041: ObsoleteAttribute 메시지를 제공하십시오.](ca1041-provide-obsoleteattribute-message.md)
##### [CA1043: 인덱서에 정수 또는 문자열 인수를 사용하십시오.](ca1043-use-integral-or-string-argument-for-indexers.md)
##### [CA1044: 속성은 쓰기 전용이면 안 됩니다.](ca1044-properties-should-not-be-write-only.md)
##### [CA1045: 참조로 참조 형식을 전달하지 않습니다.](ca1045-do-not-pass-types-by-reference.md)
##### [CA1046: 참조 형식에 같음 연산자를 오버로드하지 마십시오.](ca1046-do-not-overload-operator-equals-on-reference-types.md)
##### [CA1047: protected 멤버를 sealed 형식으로 선언하지 마십시오.](ca1047-do-not-declare-protected-members-in-sealed-types.md)
##### [CA1048: 가상 멤버를 sealed 형식으로 선언하지 마십시오.](ca1048-do-not-declare-virtual-members-in-sealed-types.md)
##### [CA1049: 네이티브 리소스가 있는 형식은 삭제 가능해야 합니다.](ca1049-types-that-own-native-resources-should-be-disposable.md)
##### [CA1050: 네임스페이스에 형식을 선언하십시오.](ca1050-declare-types-in-namespaces.md)
##### [CA1051: 표시되는 인스턴스 필드를 선언하지 마십시오.](ca1051-do-not-declare-visible-instance-fields.md)
##### [CA1052: 정적 소유자 형식은 sealed여야 합니다.](ca1052-static-holder-types-should-be-sealed.md)
##### [CA1053: 정적 소유자 형식에는 생성자를 사용하면 안 됩니다.](ca1053-static-holder-types-should-not-have-constructors.md)
##### [CA1054: URI 매개 변수는 문자열이면 안 됩니다.](ca1054-uri-parameters-should-not-be-strings.md)
##### [CA1055: URI 반환 값은 문자열이면 안 됩니다.](ca1055-uri-return-values-should-not-be-strings.md)
##### [CA1056: URI 속성은 문자열이면 안 됩니다.](ca1056-uri-properties-should-not-be-strings.md)
##### [CA1057: 문자열 URI 오버로드는 System.Uri 오버로드를 호출합니다.](ca1057-string-uri-overloads-call-system-uri-overloads.md)
##### [CA1058: 형식은 특정 기본 형식을 확장하면 안 됩니다.](ca1058-types-should-not-extend-certain-base-types.md)
##### [CA1059: 멤버는 구체적인 특정 형식을 노출하면 안 됩니다.](ca1059-members-should-not-expose-certain-concrete-types.md)
##### [CA1060: P-Invoke를 NativeMethods 클래스로 이동](ca1060-move-p-invokes-to-nativemethods-class.md)
##### [CA1061: 기본 클래스 메서드를 숨기지 마십시오.](ca1061-do-not-hide-base-class-methods.md)
##### [CA1062: public 메서드의 인수의 유효성을 검사하십시오.](ca1062-validate-arguments-of-public-methods.md)
##### [CA1063: IDisposable을 올바르게 구현하십시오.](ca1063-implement-idisposable-correctly.md)
##### [CA1064: 예외는 public이어야 합니다.](ca1064-exceptions-should-be-public.md)
##### [CA1065: 예기치 않은 위치에서 예외를 발생시키지 마십시오.](ca1065-do-not-raise-exceptions-in-unexpected-locations.md)
##### [CA2210: 어셈블리에는 올바른 강력한 이름을 사용해야 합니다.](ca2210-assemblies-should-have-valid-strong-names.md)
#### [전역화 경고](globalization-warnings.md)
##### [CA1300: MessageBoxOptions를 지정하십시오.](ca1300-specify-messageboxoptions.md)
##### [CA1301: 중복 액셀러레이터 키를 사용하지 마십시오.](ca1301-avoid-duplicate-accelerators.md)
##### [CA1302: 로캘별 문자열을 하드 코딩하지 마십시오.](ca1302-do-not-hardcode-locale-specific-strings.md)
##### [CA1303: 리터럴을 지역화된 매개 변수로 전달하지 마십시오.](ca1303-do-not-pass-literals-as-localized-parameters.md)
##### [CA1304: CultureInfo를 지정하십시오.](ca1304-specify-cultureinfo.md)
##### [CA1305: IFormatProvider를 지정하십시오.](ca1305-specify-iformatprovider.md)
##### [CA1306: 데이터 형식에 맞는 로캘을 설정하십시오.](ca1306-set-locale-for-data-types.md)
##### [CA1307: StringComparison을 지정하십시오.](ca1307-specify-stringcomparison.md)
##### [CA1308: 문자열을 대문자로 정규화하십시오.](ca1308-normalize-strings-to-uppercase.md)
##### [CA1309: 서수 StringComparison을 사용하십시오.](ca1309-use-ordinal-stringcomparison.md)
##### [CA2101: P-Invoke 문자열 인수에 대해 마샬링을 지정하십시오.](ca2101-specify-marshaling-for-p-invoke-string-arguments.md)
#### [상호 운용성 경고](interoperability-warnings.md)
##### [CA1400: P-Invoke 진입점이 있어야 합니다.](ca1400-p-invoke-entry-points-should-exist.md)
##### [CA1401: P-Invoke는 노출되지 않아야 합니다.](ca1401-p-invokes-should-not-be-visible.md)
##### [CA1402: COM 노출 인터페이스에서 오버로드를 사용하지 마십시오.](ca1402-avoid-overloads-in-com-visible-interfaces.md)
##### [CA1403: 자동 레이아웃 형식은 COM 노출이면 안 됩니다.](ca1403-auto-layout-types-should-not-be-com-visible.md)
##### [CA1404: P-Invoke 다음에 바로 GetLastError를 호출하십시오.](ca1404-call-getlasterror-immediately-after-p-invoke.md)
##### [CA1405: COM 노출 형식의 기본 형식은 COM 노출이어야 합니다.](ca1405-com-visible-type-base-types-should-be-com-visible.md)
##### [CA1406: Visual Basic 6 클라이언트에서 Int64 인수를 사용하지 않습니다.](ca1406-avoid-int64-arguments-for-visual-basic-6-clients.md)
##### [CA1407: COM 노출 형식에 정적 멤버를 사용하지 마십시오.](ca1407-avoid-static-members-in-com-visible-types.md)
##### [CA1408: AutoDual ClassInterfaceType을 사용하지 마십시오.](ca1408-do-not-use-autodual-classinterfacetype.md)
##### [CA1409: COM 노출 형식을 만들 수 있어야 합니다.](ca1409-com-visible-types-should-be-creatable.md)
##### [CA1410: COM 등록 메서드는 일치해야 합니다.](ca1410-com-registration-methods-should-be-matched.md)
##### [CA1411: COM 등록 메서드는 노출되면 안 됩니다.](ca1411-com-registration-methods-should-not-be-visible.md)
##### [CA1412: ComSource 인터페이스를 IDispatch로 표시하십시오.](ca1412-mark-comsource-interfaces-as-idispatch.md)
##### [CA1413: Com 노출 값 형식에 public이 아닌 필드를 사용하지 마십시오.](ca1413-avoid-non-public-fields-in-com-visible-value-types.md)
##### [CA1414: 부울 P/Invoke 인수를 MarshalAs로 표시하십시오.](ca1414-mark-boolean-p-invoke-arguments-with-marshalas.md)
##### [CA1415: P-Invoke를 올바르게 선언하십시오.](ca1415-declare-p-invokes-correctly.md)
#### [유지 관리 경고](maintainability-warnings.md)
##### [CA1500: 변수 이름은 필드 이름과 달라야 합니다.](ca1500-variable-names-should-not-match-field-names.md)
##### [CA1501: 상속성을 너무 많이 사용하지 마십시오.](ca1501-avoid-excessive-inheritance.md)
##### [CA1502: 지나치게 복잡하게 만들지 마십시오.](ca1502-avoid-excessive-complexity.md)
##### [CA1504: 잘못된 필드 이름을 검토하십시오.](ca1504-review-misleading-field-names.md)
##### [CA1505: 유지 관리할 수 없는 코드는 사용하지 마십시오.](ca1505-avoid-unmaintainable-code.md)
##### [CA1506: 클래스 결합을 지나치게 많이 사용하지 마십시오.](ca1506-avoid-excessive-class-coupling.md)
#### [이동성 경고](mobility-warnings.md)
##### [CA1600: 유휴 상태 프로세스 우선 순위를 사용하지 마십시오.](ca1600-do-not-use-idle-process-priority.md)
##### [CA1601: 전원 상태 변경을 방해하는 타이머를 사용하지 마십시오.](ca1601-do-not-use-timers-that-prevent-power-state-changes.md)
#### [이름 지정 경고](naming-warnings.md)
##### [CA1700: 열거형 값의 이름을 'Reserved'로 지정하지 마십시오.](ca1700-do-not-name-enum-values-reserved.md)
##### [CA1701: 리소스 문자열 복합 단어는 정확한 대/소문자를 사용해야 합니다.](ca1701-resource-string-compound-words-should-be-cased-correctly.md)
##### [CA1702: 복합 단어는 정확한 대/소문자를 사용해야 합니다.](ca1702-compound-words-should-be-cased-correctly.md)
##### [CA1703: 리소스 문자열에는 정확한 철자를 사용해야 합니다.](ca1703-resource-strings-should-be-spelled-correctly.md)
##### [CA1704: 식별자에는 정확한 철자를 사용해야 합니다.](ca1704-identifiers-should-be-spelled-correctly.md)
##### [CA1707: 식별자에는 밑줄을 사용할 수 없습니다.](ca1707-identifiers-should-not-contain-underscores.md)
##### [CA1708: 식별자에는 대/소문자만 다른 이름을 사용할 수 없습니다.](ca1708-identifiers-should-differ-by-more-than-case.md)
##### [CA1709: 식별자는 정확한 대/소문자를 사용해야 합니다.](ca1709-identifiers-should-be-cased-correctly.md)
##### [CA1710: 식별자에는 올바른 접미사를 사용해야 합니다.](ca1710-identifiers-should-have-correct-suffix.md)
##### [CA1711: 식별자에는 올바른 접미사를 사용해야 합니다.](ca1711-identifiers-should-not-have-incorrect-suffix.md)
##### [CA1712: 열거형 값에 형식 이름을 접두사로 사용하지 마십시오.](ca1712-do-not-prefix-enum-values-with-type-name.md)
##### [CA1713: 이벤트에 Before 또는 After 접두사를 사용하지 마십시오.](ca1713-events-should-not-have-before-or-after-prefix.md)
##### [CA1714: 플래그 열거형에는 복수형 이름을 사용해야 합니다.](ca1714-flags-enums-should-have-plural-names.md)
##### [CA1715: 식별자에는 올바른 접두사를 사용해야 합니다.](ca1715-identifiers-should-have-correct-prefix.md)
##### [CA1716: 식별자는 키워드와 달라야 합니다.](ca1716-identifiers-should-not-match-keywords.md)
##### [CA1717: FlagsAttribute 열거형에만 복수형 이름을 사용해야 합니다.](ca1717-only-flagsattribute-enums-should-have-plural-names.md)
##### [CA1719: 매개 변수 이름은 멤버 이름과 달라야 합니다.](ca1719-parameter-names-should-not-match-member-names.md)
##### [CA1720: 식별자에 형식 이름을 포함하면 안 됩니다.](ca1720-identifiers-should-not-contain-type-names.md)
##### [CA1721: 속성 이름은 Get 메서드와 달라야 합니다.](ca1721-property-names-should-not-match-get-methods.md)
##### [CA1722: 식별자에는 올바른 접두사를 사용해야 합니다.](ca1722-identifiers-should-not-have-incorrect-prefix.md)
##### [CA1725: 매개 변수 이름은 기본 선언과 일치해야 합니다.](ca1725-parameter-names-should-match-base-declaration.md)
##### [CA1724: 형식 이름은 네임스페이스와 달라야 합니다.](ca1724-type-names-should-not-match-namespaces.md)
##### [CA1726: 기본 설정 용어를 사용하십시오.](ca1726-use-preferred-terms.md)
#### [성능 경고](performance-warnings.md)
##### [CA1800: 불필요하게 캐스팅하지 마십시오.](ca1800-do-not-cast-unnecessarily.md)
##### [CA1802: 가능하면 리터럴을 사용하십시오.](ca1802-use-literals-where-appropriate.md)
##### [CA1804: 사용되지 않는 로컬 항목을 제거하십시오.](ca1804-remove-unused-locals.md)
##### [CA1809: 불필요한 로컬 항목을 사용하지 마십시오.](ca1809-avoid-excessive-locals.md)
##### [CA1810: 참조 형식 정적 필드를 인라인으로 초기화하십시오.](ca1810-initialize-reference-type-static-fields-inline.md)
##### [CA1811: 호출되지 않는 전용 코드를 사용하지 마십시오.](ca1811-avoid-uncalled-private-code.md)
##### [CA1812: 인스턴스화되지 않은 내부 클래스를 사용하지 마십시오.](ca1812-avoid-uninstantiated-internal-classes.md)
##### [CA1813: 봉인되지 않은 특성을 사용하지 마십시오.](ca1813-avoid-unsealed-attributes.md)
##### [CA1814: 다차원 배열보다 가변 배열을 사용하십시오.](ca1814-prefer-jagged-arrays-over-multidimensional.md)
##### [CA1815: 값 형식에서 Equals 또는 같음 연산자를 재정의하십시오.](ca1815-override-equals-and-operator-equals-on-value-types.md)
##### [CA1819: 속성은 배열을 반환해서는 안 됩니다.](ca1819-properties-should-not-return-arrays.md)
##### [CA1820: 문자열 길이를 사용하여 문자열이 비었는지 테스트하십시오.](ca1820-test-for-empty-strings-using-string-length.md)
##### [CA1821: 빈 종료자를 제거하십시오.](ca1821-remove-empty-finalizers.md)
##### [CA1822: 멤버를 static으로 표시하십시오.](ca1822-mark-members-as-static.md)
##### [CA1823: 사용되지 않는 전용 필드를 사용하지 마십시오.](ca1823-avoid-unused-private-fields.md)
##### [CA1824: 어셈블리를 NeutralResourcesLanguageAttribute로 표시하십시오.](ca1824-mark-assemblies-with-neutralresourceslanguageattribute.md)
#### [이식성 경고](portability-warnings.md)
##### [CA1900: 값 형식 필드는 이식 가능해야 합니다.](ca1900-value-type-fields-should-be-portable.md)
##### [CA1901: P-Invoke 선언은 이식 가능해야 합니다.](ca1901-p-invoke-declarations-should-be-portable.md)
##### [CA1903: 대상 프레임워크에서 API만 사용하십시오.](ca1903-use-only-api-from-targeted-framework.md)
#### [안정성 경고](reliability-warnings.md)
##### [CA2000: 범위를 벗어나기 전에 개체를 삭제하십시오.](ca2000-dispose-objects-before-losing-scope.md)
##### [CA2001: 문제가 있는 메서드는 호출하지 마십시오.](ca2001-avoid-calling-problematic-methods.md)
##### [CA2002: 약한 ID를 가진 개체를 잠그지 마십시오.](ca2002-do-not-lock-on-objects-with-weak-identity.md)
##### [CA2003: 파이버를 스레드로 취급하지 마십시오.](ca2003-do-not-treat-fibers-as-threads.md)
##### [CA2004: GC.KeepAlive에 대한 호출을 제거하십시오.](ca2004-remove-calls-to-gc-keepalive.md)
##### [CA2006: SafeHandle을 사용하여 네이티브 리소스를 캡슐화하십시오.](ca2006-use-safehandle-to-encapsulate-native-resources.md)
#### [보안 경고](security-warnings.md)
##### [CA2100: 보안상 취약한 부분이 있는지 SQL 쿼리를 검토하십시오.](ca2100-review-sql-queries-for-security-vulnerabilities.md)
##### [CA2102: 일반 처리기에서 비 CLSCompliant 예외를 catch하십시오.](ca2102-catch-non-clscompliant-exceptions-in-general-handlers.md)
##### [CA2103: 명령적 보안을 검토하십시오.](ca2103-review-imperative-security.md)
##### [CA2104: 변경 가능한 읽기 전용 참조 형식을 선언하지 마십시오.](ca2104-do-not-declare-read-only-mutable-reference-types.md)
##### [CA2105: 배열 필드는 읽기 전용이면 안 됩니다.](ca2105-array-fields-should-not-be-read-only.md)
##### [CA2106: 어설션을 안전하게 하십시오.](ca2106-secure-asserts.md)
##### [CA2107: Deny 및 PermitOnly 사용을 검토하십시오.](ca2107-review-deny-and-permit-only-usage.md)
##### [CA2108: 값 형식에서 선언적 보안을 검토하십시오.](ca2108-review-declarative-security-on-value-types.md)
##### [CA2109: 표시되는 이벤트 처리기를 검토하십시오.](ca2109-review-visible-event-handlers.md)
##### [CA2111: 포인터는 노출되면 안 됩니다.](ca2111-pointers-should-not-be-visible.md)
##### [CA2112: 보안 형식은 필드를 노출하면 안 됩니다.](ca2112-secured-types-should-not-expose-fields.md)
##### [CA2114: 메서드 보안은 형식의 상위 집합이어야 합니다.](ca2114-method-security-should-be-a-superset-of-type.md)
##### [CA2115: 네이티브 리소스를 사용하는 경우에는 GC.KeepAlive를 호출하십시오.](ca2115-call-gc-keepalive-when-using-native-resources.md)
##### [CA2116: APTCA 메서드는 APTCA 메서드만 호출해야 합니다.](ca2116-aptca-methods-should-only-call-aptca-methods.md)
##### [CA2117: APTCA 형식은 APTCA 기본 형식만 확장해야 합니다.](ca2117-aptca-types-should-only-extend-aptca-base-types.md)
##### [CA2118: SuppressUnmanagedCodeSecurityAttribute 사용을 검토하십시오.](ca2118-review-suppressunmanagedcodesecurityattribute-usage.md)
##### [CA2119: private 인터페이스를 만족하는 메서드를 봉인하십시오.](ca2119-seal-methods-that-satisfy-private-interfaces.md)
##### [CA2120: serialization 생성자를 안전하게 하십시오.](ca2120-secure-serialization-constructors.md)
##### [CA2121: 정적 생성자는 private이어야 합니다.](ca2121-static-constructors-should-be-private.md)
##### [CA2122: 링크 요청이 있는 메서드를 간접적으로 노출하지 마십시오.](ca2122-do-not-indirectly-expose-methods-with-link-demands.md)
##### [CA2123: 재정의 링크 요청은 기본 형식의 링크 요청과 같아야 합니다.](ca2123-override-link-demands-should-be-identical-to-base.md)
##### [CA2124: 취약한 finally 절을 외부 try에 래핑하십시오.](ca2124-wrap-vulnerable-finally-clauses-in-outer-try.md)
##### [CA2126: 형식 링크 요청에는 상속 요청이 필요합니다.](ca2126-type-link-demands-require-inheritance-demands.md)
##### [CA2130: 보안 위험 상수는 투명해야 합니다.](ca2130-security-critical-constants-should-be-transparent.md)
##### [CA2131: 보안에 중요한 형식은 형식 등가에 참여할 수 없습니다.](ca2131-security-critical-types-may-not-participate-in-type-equivalence.md)
##### [CA2132: 기본 생성자는 최소한 기본 형식 기본 생성자만큼 중요해야 합니다.](ca2132-default-constructors-must-be-at-least-as-critical-as-base-type-default-constructors.md)
##### [CA2133: 대리인은 투명도가 일관된 메서드에 바인딩해야 합니다.](ca2133-delegates-must-bind-to-methods-with-consistent-transparency.md)
##### [CA2134: 메서드는 기본 메서드를 재정의할 때 일관성 있는 방식을 유지해야 합니다.](ca2134-methods-must-keep-consistent-transparency-when-overriding-base-methods.md)
##### [CA2135: 수준 2 어셈블리는 LinkDemands를 포함해서는 안 됩니다.](ca2135-level-2-assemblies-should-not-contain-linkdemands.md)
##### [CA2136: 멤버는 충돌하는 투명도 주석을 가져서는 안 됩니다.](ca2136-members-should-not-have-conflicting-transparency-annotations.md)
##### [CA2137: 투명한 메서드는 안정형 IL만 포함해야 합니다.](ca2137-transparent-methods-must-contain-only-verifiable-il.md)
##### [CA2138: 투명한 메서드는 SuppressUnmanagedCodeSecurity 특성을 가진 메서드를 호출해서는 안 됩니다.](ca2138-transparent-methods-must-not-call-methods-with-the-suppressunmanagedcodesecurity-attribute.md)
##### [CA2139: 투명한 메서드는 HandleProcessCorruptingExceptions 특성을 사용할 수 없습니다.](ca2139-transparent-methods-may-not-use-the-handleprocesscorruptingexceptions-attribute.md)
##### [CA2140: 투명 코드는 보안에 중요한 항목을 참조해서는 안 됩니다.](ca2140-transparent-code-must-not-reference-security-critical-items.md)
##### [CA2141: 투명한 메서드는 LinkDemands를 충족해서는 안 됩니다.](ca2141-transparent-methods-must-not-satisfy-linkdemands.md)
##### [CA2142: 투명한 코드는 LinkDemands를 사용하여 보호해서는 안 됩니다.](ca2142-transparent-code-should-not-be-protected-with-linkdemands.md)
##### [CA2143: 투명한 메서드는 보안 요청을 사용해서는 안 됩니다.](ca2143-transparent-methods-should-not-use-security-demands.md)
##### [CA2144: 투명 코드는 바이트 배열에서 어셈블리를 로드해서는 안 됩니다.](ca2144-transparent-code-should-not-load-assemblies-from-byte-arrays.md)
##### [CA2145: 투명한 메서드는 SuppressUnmanagedCodeSecurityAttribute로 데코레이팅해서는 안 됩니다.](ca2145-transparent-methods-should-not-be-decorated-with-the-suppressunmanagedcodesecurityattribute.md)
##### [CA2146: 형식은 최소한 기본 형식 및 인터페이스만큼 중요해야 합니다.](ca2146-types-must-be-at-least-as-critical-as-their-base-types-and-interfaces.md)
##### [CA2147: 투명 메서드는 보안 어설션을 사용할 수 없습니다.](ca2147-transparent-methods-may-not-use-security-asserts.md)
##### [CA2149: 투명한 메서드는 네이티브 코드를 호출해서는 안 됩니다.](ca2149-transparent-methods-must-not-call-into-native-code.md)
##### [CA2151: 중요한 형식이 포함된 필드는 보안에 중요한 필드여야 함](ca2151-fields-with-critical-types-should-be-security-critical.md)
##### [CA5122 P-Invoke 선언은 안전에 중요한 선언이 아니어야 함](ca5122-p-invoke-declarations-should-not-be-safe-critical.md)
##### [CA2153: 손상된 상태 예외 처리 방지](ca2153-avoid-handling-corrupted-state-exceptions.md)
##### [CA3075: 안전하지 않은 DTD 처리](ca3075-insecure-dtd-processing.md)
##### [CA3076: 안전하지 않은 XSLT 스크립트 실행](ca3076-insecure-xslt-script-execution.md)
##### [CA3077: API 디자인, XML 문서 및 XML 텍스트 판독기의 안전하지 않은 처리](ca3077-insecure-processing-in-api-design-xml-document-and-xml-text-reader.md)
#### [사용법 경고](usage-warnings.md)
##### [CA1801: 사용되지 않은 매개 변수를 검토하십시오.](ca1801-review-unused-parameters.md)
##### [CA1806: 메서드 결과를 무시하지 마십시오.](ca1806-do-not-ignore-method-results.md)
##### [CA1816: GC.SuppressFinalize를 올바르게 호출하십시오.](ca1816-call-gc-suppressfinalize-correctly.md)
##### [CA2200: 스택 정보를 유지하도록 다시 throw하십시오.](ca2200-rethrow-to-preserve-stack-details.md)
##### [CA2201: 예약된 예외 형식을 발생시키지 마십시오.](ca2201-do-not-raise-reserved-exception-types.md)
##### [CA2202: 개체를 여러 번 삭제하지 마십시오.](ca2202-do-not-dispose-objects-multiple-times.md)
##### [CA2204: 리터럴의 철자가 맞아야 합니다.](ca2204-literals-should-be-spelled-correctly.md)
##### [CA2205: Win32 API에 있는 동일한 기능의 관리되는 항목을 사용하십시오.](ca2205-use-managed-equivalents-of-win32-api.md)
##### [CA2207: 값 형식 정적 필드를 인라인으로 초기화하십시오.](ca2207-initialize-value-type-static-fields-inline.md)
##### [CA2208: 인수 예외를 올바르게 인스턴스화하십시오.](ca2208-instantiate-argument-exceptions-correctly.md)
##### [CA2211: 비상수 필드는 노출되면 안 됩니다.](ca2211-non-constant-fields-should-not-be-visible.md)
##### [CA2212: 서비스 구성 요소를 WebMethod를 사용하여 표시하지 마십시오.](ca2212-do-not-mark-serviced-components-with-webmethod.md)
##### [CA2213: 삭제 가능한 필드는 삭제해야 합니다.](ca2213-disposable-fields-should-be-disposed.md)
##### [CA2214: 재정의 가능한 메서드를 생성자에서 호출하지 마십시오.](ca2214-do-not-call-overridable-methods-in-constructors.md)
##### [CA2215: Dispose 메서드는 기본 클래스 Dispose를 호출해야 합니다.](ca2215-dispose-methods-should-call-base-class-dispose.md)
##### [CA2216: 삭제 가능한 형식은 종료자를 선언해야 합니다.](ca2216-disposable-types-should-declare-finalizer.md)
##### [CA2217: 열거형을 FlagsAttribute로 표시하지 마십시오.](ca2217-do-not-mark-enums-with-flagsattribute.md)
##### [CA2218: Equals를 재정의할 때 GetHashCode를 재정의하십시오.](ca2218-override-gethashcode-on-overriding-equals.md)
##### [CA2219: exception 절에서 예외를 발생시키지 마십시오.](ca2219-do-not-raise-exceptions-in-exception-clauses.md)
##### [CA2220: 종료자는 기본 클래스 종료자를 호출해야 합니다.](ca2220-finalizers-should-call-base-class-finalizer.md)
##### [CA2221: 종료자는 protected여야 합니다.](ca2221-finalizers-should-be-protected.md)
##### [CA2222: 상속된 멤버 노출 수준을 낮추지 마십시오.](ca2222-do-not-decrease-inherited-member-visibility.md)
##### [CA2223: 멤버는 반환 형식 이외의 것도 달라야 합니다.](ca2223-members-should-differ-by-more-than-return-type.md)
##### [CA2224: 같음 연산자를 오버로드할 때 Equals를 재정의하십시오.](ca2224-override-equals-on-overloading-operator-equals.md)
##### [CA2225: 연산자 오버로드에는 명명된 대체 항목이 있습니다.](ca2225-operator-overloads-have-named-alternates.md)
##### [CA2226: 연산자에는 대칭 오버로드가 있어야 합니다.](ca2226-operators-should-have-symmetrical-overloads.md)
##### [CA2227: 컬렉션 속성은 읽기 전용이어야 합니다.](ca2227-collection-properties-should-be-read-only.md)
##### [CA2228: 릴리스되지 않은 리소스 형식을 제공하지 마십시오.](ca2228-do-not-ship-unreleased-resource-formats.md)
##### [CA2229: serialization 생성자를 구현하십시오.](ca2229-implement-serialization-constructors.md)
##### [CA2230: 가변 인수로 params를 사용하십시오.](ca2230-use-params-for-variable-arguments.md)
##### [CA2231: ValueType.Equals를 재정의할 때 같음 연산자를 오버로드하십시오.](ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)
##### [CA2232: Windows Forms 진입점을 STAThread를 사용하여 표시하십시오.](ca2232-mark-windows-forms-entry-points-with-stathread.md)
##### [CA2233: 연산은 오버플로되지 않아야 합니다.](ca2233-operations-should-not-overflow.md)
##### [CA2234: 문자열 대신 System.Uri 개체를 전달하십시오.](ca2234-pass-system-uri-objects-instead-of-strings.md)
##### [CA2235: 모두 serialize할 수 없는 필드로 표시하십시오.](ca2235-mark-all-non-serializable-fields.md)
##### [CA2236: ISerializable 형식에서 기본 클래스 메서드를 호출하십시오.](ca2236-call-base-class-methods-on-iserializable-types.md)
##### [CA2237: ISerializable 형식을 SerializableAttribute로 표시하십시오.](ca2237-mark-iserializable-types-with-serializableattribute.md)
##### [CA2238: serialization 메서드를 올바르게 구현하십시오.](ca2238-implement-serialization-methods-correctly.md)
##### [CA2239: 선택적 필드에 deserialization 메서드를 제공하십시오.](ca2239-provide-deserialization-methods-for-optional-fields.md)
##### [CA2240: ISerializable을 올바르게 구현하십시오.](ca2240-implement-iserializable-correctly.md)
##### [CA2241: 형식 메서드에 올바른 인수를 제공하십시오.](ca2241-provide-correct-arguments-to-formatting-methods.md)
##### [CA2242: NaN에 대해 정확하게 테스트하십시오.](ca2242-test-for-nan-correctly.md)
##### [CA2243: 특성 문자열 리터럴이 올바르게 구문 분석되어야 합니다.](ca2243-attribute-string-literals-should-parse-correctly.md)
#### [코드 분석 정책 오류](code-analysis-policy-errors.md)
## [코드 분석을 사용하여 C/C++ 코드 품질 분석](analyzing-c-cpp-code-quality-by-using-code-analysis.md)
### [빠른 시작: C/C++용 코드 분석](quick-start-code-analysis-for-c-cpp.md)
### [규칙 집합을 사용하여 실행할 C++ 규칙 지정](using-rule-sets-to-specify-the-cpp-rules-to-run.md)
### [C++ 핵심 지침 검사기 사용](using-the-cpp-core-guidelines-checkers.md)
### [C/C++용 코드 분석 개요](code-analysis-for-c-cpp-overview.md)
### [방법: C/C++ 프로젝트의 코드 분석 속성 설정](how-to-set-code-analysis-properties-for-c-cpp-projects.md)
### [연습: C/C++ 코드의 오류 분석](walkthrough-analyzing-c-cpp-code-for-defects.md)
#### [데모 샘플](demo-sample.md)
### [C/C++ 코드 오류를 줄이기 위한 SAL 주석 사용](using-sal-annotations-to-reduce-c-cpp-code-defects.md)
#### [SAL 이해](understanding-sal.md)
#### [함수 매개 변수 및 반환 값에 주석 지정](annotating-function-parameters-and-return-values.md)
#### [함수 동작에 주석 지정](annotating-function-behavior.md)
#### [구조체 및 클래스에 주석 지정](annotating-structs-and-classes.md)
#### [잠금 동작에 주석 지정](annotating-locking-behavior.md)
#### [주석 적용 시기 및 위치 지정](specifying-when-and-where-an-annotation-applies.md)
#### [내장 함수](intrinsic-functions.md)
#### [모범 사례 및 예제(SAL)](best-practices-and-examples-sal.md)
### [방법: __analysis_assume을 사용하여 추가 코드 정보 지정](how-to-specify-additional-code-information-by-using-analysis-assume.md)
### [C/C++용 코드 분석 경고](code-analysis-for-c-cpp-warnings.md)
#### [C1250](c1250.md)
#### [C1251](c1251.md)
#### [C1252](c1252.md)
#### [C1253](c1253.md)
#### [C1254](c1254.md)
#### [C1255](c1255.md)
#### [C1256](c1256.md)
#### [C1257](c1257.md)
#### [C6001](c6001.md)
#### [C6011](c6011.md)
#### [C6014](c6014.md)
#### [C6029](c6029.md)
#### [C6031](c6031.md)
#### [C6053](c6053.md)
#### [C6054](c6054.md)
#### [C6059](c6059.md)
#### [C6063](c6063.md)
#### [C6064](c6064.md)
#### [C6066](c6066.md)
#### [C6067](c6067.md)
#### [C6101](c6101.md)
#### [C6102](c6102.md)
#### [C6103](c6103.md)
#### [C6200](c6200.md)
#### [C6201](c6201.md)
#### [C6211](c6211.md)
#### [C6214](c6214.md)
#### [C6215](c6215.md)
#### [C6216](c6216.md)
#### [C6217](c6217.md)
#### [C6219](c6219.md)
#### [C6220](c6220.md)
#### [C6221](c6221.md)
#### [C6225](c6225.md)
#### [C6226](c6226.md)
#### [C6230](c6230.md)
#### [C6235](c6235.md)
#### [C6236](c6236.md)
#### [C6237](c6237.md)
#### [C6239](c6239.md)
#### [C6240](c6240.md)
#### [C6242](c6242.md)
#### [C6244](c6244.md)
#### [C6246](c6246.md)
#### [C6248](c6248.md)
#### [C6250](c6250.md)
#### [C6255](c6255.md)
#### [C6258](c6258.md)
#### [C6259](c6259.md)
#### [C6260](c6260.md)
#### [C6262](c6262.md)
#### [C6263](c6263.md)
#### [C6268](c6268.md)
#### [C6269](c6269.md)
#### [C6270](c6270.md)
#### [C6271](c6271.md)
#### [C6272](c6272.md)
#### [C6273](c6273.md)
#### [C6274](c6274.md)
#### [C6276](c6276.md)
#### [C6277](c6277.md)
#### [C6278](c6278.md)
#### [C6279](c6279.md)
#### [C6280](c6280.md)
#### [C6281](c6281.md)
#### [C6282](c6282.md)
#### [C6283](c6283.md)
#### [C6284](c6284.md)
#### [C6285](c6285.md)
#### [C6286](c6286.md)
#### [C6287](c6287.md)
#### [C6288](c6288.md)
#### [C6289](c6289.md)
#### [C6290](c6290.md)
#### [C6291](c6291.md)
#### [C6292](c6292.md)
#### [C6293](c6293.md)
#### [C6294](c6294.md)
#### [C6295](c6295.md)
#### [C6296](c6296.md)
#### [C6297](c6297.md)
#### [C6298](c6298.md)
#### [C6299](c6299.md)
#### [C6302](c6302.md)
#### [C6303](c6303.md)
#### [C6305](c6305.md)
#### [C6306](c6306.md)
#### [C6308](c6308.md)
#### [C6310](c6310.md)
#### [C6312](c6312.md)
#### [C6313](c6313.md)
#### [C6314](c6314.md)
#### [C6315](c6315.md)
#### [C6316](c6316.md)
#### [C6317](c6317.md)
#### [C6318](c6318.md)
#### [C6319](c6319.md)
#### [C6320](c6320.md)
#### [C6322](c6322.md)
#### [C6323](c6323.md)
#### [C6324](c6324.md)
#### [C6326](c6326.md)
#### [C6328](c6328.md)
#### [C6329](c6329.md)
#### [C6330](c6330.md)
#### [C6331](c6331.md)
#### [C6332](c6332.md)
#### [C6333](c6333.md)
#### [C6334](c6334.md)
#### [C6335](c6335.md)
#### [C6336](c6336.md)
#### [C6340](c6340.md)
#### [C6381](c6381.md)
#### [C6383](c6383.md)
#### [C6384](c6384.md)
#### [C6385](c6385.md)
#### [C6386](c6386.md)
#### [C6387](c6387.md)
#### [C6388](c6388.md)
#### [C6400](c6400.md)
#### [C6401](c6401.md)
#### [C6411](c6411.md)
#### [C6412](c6412.md)
#### [C6500](c6500.md)
#### [C6501](c6501.md)
#### [C6503](c6503.md)
#### [C6504](c6504.md)
#### [C6505](c6505.md)
#### [C6506](c6506.md)
#### [C6508](c6508.md)
#### [C6509](c6509.md)
#### [C6510](c6510.md)
#### [C6511](c6511.md)
#### [C6513](c6513.md)
#### [C6514](c6514.md)
#### [C6515](c6515.md)
#### [C6516](c6516.md)
#### [C6517](c6517.md)
#### [C6518](c6518.md)
#### [C6522](c6522.md)
#### [C6525](c6525.md)
#### [C6527](c6527.md)
#### [C6530](c6530.md)
#### [C6540](c6540.md)
#### [C6551](c6551.md)
#### [C6552](c6552.md)
#### [C6701](c6701.md)
#### [C6702](c6702.md)
#### [C6703](c6703.md)
#### [C6704](c6704.md)
#### [C6705](c6705.md)
#### [C6706](c6706.md)
#### [C6707](c6707.md)
#### [C6993](c6993.md)
#### [C6995](c6995.md)
#### [C6997](c6997.md)
#### [C26100](c26100.md)
#### [C26101](c26101.md)
#### [C26105](c26105.md)
#### [C26110](c26110.md)
#### [C26111](c26111.md)
#### [C26112](c26112.md)
#### [C26115](c26115.md)
#### [C26116](c26116.md)
#### [C26117](c26117.md)
#### [C26130](c26130.md)
#### [C26135](c26135.md)
#### [C26140](c26140.md)
#### [C26160](c26160.md)
#### [C26165](c26165.md)
#### [C26166](c26166.md)
#### [C26167](c26167.md)
#### [C28020](c28020.md)
#### [C28021](c28021.md)
#### [C28022](c28022.md)
#### [C28023](c28023.md)
#### [C28024](c28024.md)
#### [C28039](c28039.md)
#### [C28103](c28103.md)
#### [C28104](c28104.md)
#### [C28105](c28105.md)
#### [C28106](c28106.md)
#### [C28107](c28107.md)
#### [C28108](c28108.md)
#### [C28109](c28109.md)
#### [C28112](c28112.md)
#### [C28113](c28113.md)
#### [C28125](c28125.md)
#### [C28137](c28137.md)
#### [C28138](c28138.md)
#### [C28159](c28159.md)
#### [C28160](c28160.md)
#### [C28163](c28163.md)
#### [C28164](c28164.md)
#### [C28182](c28182.md)
#### [C28183](c28183.md)
#### [C28193](c28193.md)
#### [C28194](c28194.md)
#### [C28195](c28195.md)
#### [C28196](c28196.md)
#### [C28197](c28197.md)
#### [C28198](c28198.md)
#### [C28199](c28199.md)
#### [C28202](c28202.md)
#### [C28203](c28203.md)
#### [C28204](c28204.md)
#### [C28205](c28205.md)
#### [C28206](c28206.md)
#### [C28207](c28207.md)
#### [C28208](c28208.md)
#### [C28209](c28209.md)
#### [C28210](c28210.md)
#### [C28211](c28211.md)
#### [C28212](c28212.md)
#### [C28213](c28213.md)
#### [C28214](c28214.md)
#### [C28215](c28215.md)
#### [C28216](c28216.md)
#### [C28217](c28217.md)
#### [C28218](c28218.md)
#### [C28219](c28219.md)
#### [C28220](c28220.md)
#### [C28221](c28221.md)
#### [C28222](c28222.md)
#### [C28223](c28223.md)
#### [C28224](c28224.md)
#### [C28225](c28225.md)
#### [C28226](c28226.md)
#### [C28227](c28227.md)
#### [C28228](c28228.md)
#### [C28229](c28229.md)
#### [C28230](c28230.md)
#### [C28231](c28231.md)
#### [C28232](c28232.md)
#### [C28233](c28233.md)
#### [C28234](c28234.md)
#### [C28235](c28235.md)
#### [C28236](c28236.md)
#### [C28237](c28237.md)
#### [C28238](c28238.md)
#### [C28239](c28239.md)
#### [C28240](c28240.md)
#### [C28241](c28241.md)
#### [C28243](c28243.md)
#### [C28244](c28244.md)
#### [C28245](c28245.md)
#### [C28246](c28246.md)
#### [C28250](c28250.md)
#### [C28251](c28251.md)
#### [C28252](c28252.md)
#### [C28253](c28253.md)
#### [C28254](c28254.md)
#### [C28262](c28262.md)
#### [C28263](c28263.md)
#### [C28267](c28267.md)
#### [C28272](c28272.md)
#### [C28273](c28273.md)
#### [C28275](c28275.md)
#### [C28278](c28278.md)
#### [C28279](c28279.md)
#### [C28280](c28280.md)
#### [C28282](c28282.md)
#### [C28283](c28283.md)
#### [C28284](c28284.md)
#### [C28285](c28285.md)
#### [C28286](c28286.md)
#### [C28287](c28287.md)
#### [C28288](c28288.md)
#### [C28289](c28289.md)
#### [C28290](c28290.md)
#### [C28291](c28291.md)
#### [C28300](c28300.md)
#### [C28301](c28301.md)
#### [C28302](c28302.md)
#### [C28303](c28303.md)
#### [C28304](c28304.md)
#### [C28305](c28305.md)
#### [C28306](c28306.md)
#### [C28307](c28307.md)
#### [C28308](c28308.md)
#### [C28309](c28309.md)
#### [C28310](c28310.md)
#### [C28311](c28311.md)
#### [C28312](c28312.md)
#### [C28350](c28350.md)
#### [C28351](c28351.md)
## [규칙 집합을 사용하여 코드 분석 규칙 그룹화](using-rule-sets-to-group-code-analysis-rules.md)
### [연습: 사용자 지정 규칙 집합 구성 및 사용](walkthrough-configuring-and-using-a-custom-rule-set.md)
### [방법: 관리 코드 프로젝트에 대한 코드 분석 구성](how-to-configure-code-analysis-for-a-managed-code-project.md)
### [방법: ASP.NET 웹 응용 프로그램에 대한 코드 분석 구성](how-to-configure-code-analysis-for-an-aspnet-web-application.md)
### [방법: 코드 프로젝트 규칙 집합을 팀 프로젝트 체크 인 정책과 동기화](how-to-synchronize-code-project-rule-sets-with-team-project-check-in-policy.md)
### [방법: 솔루션의 여러 프로젝트에 대한 관리 코드 규칙 집합 지정](how-to-specify-managed-code-rule-sets-for-multiple-projects-in-a-solution.md)
### [사용자 지정 코드 분석 규칙 집합 만들기](creating-custom-code-analysis-rule-sets.md)
#### [방법: 사용자 지정 규칙 집합 만들기](how-to-create-a-custom-rule-set.md)
#### [코드 분석 규칙 집합 편집기에서 작업](working-in-the-code-analysis-rule-set-editor.md)
### [코드 분석 규칙 집합 참조](code-analysis-rule-set-reference.md)
#### [모든 규칙 규칙 집합](all-rules-rule-set.md)
#### [관리 코드에 대한 기본 수정 규칙 규칙 집합](basic-correctness-rules-rule-set-for-managed-code.md)
#### [관리 코드에 대한 기본 디자인 지침 규칙 규칙 집합](basic-design-guideline-rules-rule-set-for-managed-code.md)
#### [관리 코드에 대한 확장 수정 규칙 규칙 집합](extended-correctness-rules-rule-set-for-managed-code.md)
#### [관리 코드에 대한 확장 디자인 지침 규칙 규칙 집합](extended-design-guidelines-rules-rule-set-for-managed-code.md)
#### [관리 코드에 대한 전역화 규칙 규칙 집합](globalization-rules-rule-set-for-managed-code.md)
#### [관리 코드에 대한 관리 최소 규칙 규칙 집합](managed-minimun-rules-rule-set-for-managed-code.md)
#### [관리 코드에 대한 관리 권장 규칙 규칙 집합](managed-recommended-rules-rule-set-for-managed-code.md)
#### [혼합 최소 규칙 규칙 집합](mixed-minimum-rules-rule-set.md)
#### [혼합 권장 규칙 규칙 집합](mixed-recommended-rules-rule-set.md)
#### [네이티브 최소 규칙 규칙 집합](native-minimum-rules-rule-set.md)
#### [네이티브 권장 규칙 규칙 집합](native-recommended-rules-rule-set.md)
#### [관리 코드에 대한 보안 규칙 규칙 집합](security-rules-rule-set-for-managed-code.md)
## [코드 분석 응용 프로그램 오류](code-analysis-application-errors.md)
## [팀 프로젝트 체크 인 정책을 사용하여 코드 품질 향상](enhancing-code-quality-with-team-project-check-in-policies.md)
### [코드 분석 체크 인 정책 만들기 및 사용](creating-and-using-code-analysis-check-in-policies.md)
#### [방법: 표준 코드 분석 체크 인 정책 만들기 또는 업데이트](how-to-create-or-update-standard-code-analysis-check-in-policies.md)
#### [관리 코드에 대한 사용자 지정 코드 분석 체크 인 정책 구현](implementing-custom-code-analysis-check-in-policies-for-managed-code.md)
#### [방법: 코드 분석 체크 인 정책을 통해 유지 관리할 수 있는 코드 적용](how-to-enforce-maintainable-code-with-a-code-analysis-check-in-policy.md)
#### [코드 분석 체크 인 정책에 대한 버전 호환성](version-compatibility-for-code-analysis-check-in-policies.md)
# [관리 코드의 복잡성 및 유지 관리 용이성 측정](measuring-complexity-and-maintainability-of-managed-code.md)
## [코드 메트릭 값](code-metrics-values.md)
## [방법: 코드 메트릭 데이터 생성](how-to-generate-code-metrics-data.md)
## [코드 메트릭 데이터 작업](working-with-code-metrics-data.md)
# [품질 도구 문제 해결](troubleshooting-quality-tools.md)
## [코드 분석 문제 해결](troubleshooting-code-analysis-issues.md)
## [코드 메트릭 문제 해결](troubleshooting-code-metrics-issues.md)