---
title: FxCop 규칙 포트 상태
ms.date: 05/21/2019
ms.topic: reference
helpviewer_keywords:
- fxcop rules
- fxcop analyzers, ported rules
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 4a458a50be6161e320b3ffbbe702e21f9f502c77
ms.sourcegitcommit: 74c5360186731de07828764eb32ea1033a8c2275
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/03/2019
ms.locfileid: "67559676"
---
# <a name="fxcop-rule-port-status"></a>Fxcop 규칙 포트 상태

이전에 정적 코드 분석을 사용 하는 Visual Studio의 이전 버전의 경우 궁금할 것으로 현재 구현에서 사용할 수 있는 규칙 [FxCop 분석기](install-fxcop-analyzers.md)합니다. 이 페이지는 아직 이식 되었으며 이식 하는 규칙을 나열 되는지 이식할 예정입니다.

## <a name="ported-rules"></a>포팅된 규칙

합니다 [자동으로 생성 된 설명서 페이지](https://github.com/dotnet/roslyn-analyzers/blob/master/src/Microsoft.CodeAnalysis.FxCopAnalyzers/Microsoft.CodeAnalysis.FxCopAnalyzers.md) roslyn 분석기 리포지토리에 FxCop 분석기에 이식 되었으며 하는 규칙의 최신 목록입니다. 해당 페이지에는 역시 기본적으로 규칙을 사용할지에 연결 된 경우 등의 추가 정보 *코드 수정 사항을*합니다. ([코드 수정을](../ide/quick-actions.md) 원클릭 수정 Visual Studio에서 전구 아이콘 메뉴에서 사용할 수 있습니다.)

이 페이지에서 날짜를 기준으로 목록을 FxCop 규칙에 이식 되었으며 [FxCop 분석기](install-fxcop-analyzers.md) 포함 되어 있습니다.

규칙 ID | 제목
--------|---------
[CA1000](ca1000-do-not-declare-static-members-on-generic-types.md) | 정적 멤버를 제네릭 형식으로 선언하지 마세요.
[CA1001](ca1001-types-that-own-disposable-fields-should-be-disposable.md) | 삭제 가능한 필드가 있는 형식은 삭제 가능해야 합니다.
[CA1003](ca1003-use-generic-event-handler-instances.md) | 제네릭 이벤트 처리기 인스턴스를 사용하세요.
[CA1008](ca1008-enums-should-have-zero-value.md) | 열거형에는 0 값이 있어야 합니다.
[CA1010](ca1010-collections-should-implement-generic-interface.md) | 컬렉션은 제네릭 인터페이스를 구현해야 합니다.
[CA1012](ca1012-abstract-types-should-not-have-constructors.md) | 추상 형식에는 생성자를 사용하면 안 됩니다.
[CA1014](ca1014-mark-assemblies-with-clscompliantattribute.md) | CLSCompliant로 어셈블리 표시
[CA1016](ca1016-mark-assemblies-with-assemblyversionattribute.md) | 어셈블리 버전을 사용 하 여 어셈블리 표시
[CA1017](ca1017-mark-assemblies-with-comvisibleattribute.md) | ComVisible로 어셈블리 표시
[CA1018](ca1018-mark-attributes-with-attributeusageattribute.md) | AttributeUsageAttribute로 특성을 표시하세요.
[CA1019](ca1019-define-accessors-for-attribute-arguments.md) | 특성 인수의 접근자를 정의하세요.
[CA1024](ca1024-use-properties-where-appropriate.md) | 적합한 속성을 사용하세요.
[CA1027](ca1027-mark-enums-with-flagsattribute.md) | 열거형을 FlagsAttribute로 표시하세요.
[CA1028](ca1028-enum-storage-should-be-int32.md) | 열거형 저장소는 Int32 여야 합니다.
[CA1030](ca1030-use-events-where-appropriate.md) | 적절한 경우 이벤트를 사용하세요.
[CA1031](ca1031-do-not-catch-general-exception-types.md) | 일반적인 예외 형식을 catch하지 마세요.
[CA1032](ca1032-implement-standard-exception-constructors.md) | 표준 예외 생성자를 구현하세요.
[CA1033](ca1033-interface-methods-should-be-callable-by-child-types.md) | 인터페이스 메서드는 자식 형식에서 호출할 수 있어야 합니다.
[CA1034](ca1034-nested-types-should-not-be-visible.md) | 중첩 형식은 노출되면 안 됩니다.
[CA1036](ca1036-override-methods-on-comparable-types.md) | 비교 가능한 형식에 메서드를 재정의하세요.
[CA1040](ca1040-avoid-empty-interfaces.md) | 빈 인터페이스를 사용하지 마세요.
[CA1041](ca1041-provide-obsoleteattribute-message.md) | ObsoleteAttribute 메시지를 제공하세요.
[CA1043](ca1043-use-integral-or-string-argument-for-indexers.md) | 정수 계열 또는 인덱서에 대 한 문자열 인수를 사용 합니다.
[CA1044](ca1044-properties-should-not-be-write-only.md) | 속성은 쓰기 전용이면 안 됩니다.
[CA1050](ca1050-declare-types-in-namespaces.md) | 네임스페이스에 형식을 선언하세요.
[CA1051](ca1051-do-not-declare-visible-instance-fields.md) | 표시되는 인스턴스 필드를 선언하지 마세요.
[CA1052](ca1052-static-holder-types-should-be-sealed.md) | 정적 소유자 형식은 정적 이어야 합니다. 또는 NotInheritable (이 표 아래 참고 참조)
[CA1053](ca1053-static-holder-types-should-not-have-constructors.md) | 정적 소유자 형식에는 생성자 (이 표 아래 참고 참조)를 사용 해야 합니다.
[CA1054](ca1054-uri-parameters-should-not-be-strings.md) | Uri 매개 변수는 문자열이 면 안 됩니다.
[CA1055](ca1055-uri-return-values-should-not-be-strings.md) | Uri 반환 값은 문자열이 면 안 됩니다.
[CA1056](ca1056-uri-properties-should-not-be-strings.md) | Uri 속성은 문자열이 면 안 됩니다.
[CA1058](ca1058-types-should-not-extend-certain-base-types.md) | 형식은 특정 기본 형식을 확장하면 안 됩니다.
[CA1060](ca1060-move-p-invokes-to-nativemethods-class.md) | 네이티브 메서드 클래스 때문 이동
[CA1061](ca1061-do-not-hide-base-class-methods.md) | 기본 클래스 메서드를 숨기지 마십시오.
[CA1062](ca1062-validate-arguments-of-public-methods.md) | public 메서드의 인수에 대한 유효성을 검사하세요.
[CA1063](ca1063-implement-idisposable-correctly.md) | IDisposable을 올바르게 구현
[CA1064](ca1064-exceptions-should-be-public.md) | 예외는 public이어야 합니다.
[CA1065](ca1065-do-not-raise-exceptions-in-unexpected-locations.md) | 예기치 않은 위치에서 예외를 발생시키지 마십시오.
CA1066 | 형식 {0} IEquatable를 구현 해야\<T > Equals를 재정의 하기 때문에
CA1067 | Object.Equals(object) IEquatable를 구현 하는 경우 재정의\<T >
CA1068 | CancellationToken 매개 변수는 마지막 이어야 합니다.
CA1200 | Cref 태그를 사용 하 여 접두사를 사용 하 여 방지
[CA1303](ca1303-do-not-pass-literals-as-localized-parameters.md) | 리터럴을 지역화된 매개 변수로 전달하지 마세요.
[CA1304](ca1304-specify-cultureinfo.md) | CultureInfo를 지정하세요.
[CA1305](ca1305-specify-iformatprovider.md) | IFormatProvider를 지정하세요.
[CA1307](ca1307-specify-stringcomparison.md) | StringComparison 지정하세요.
[CA1308](ca1308-normalize-strings-to-uppercase.md) | 대문자로 문자열을 정규화하세요.
[CA1309](ca1309-use-ordinal-stringcomparison.md) | 서 수 문자열 비교를 사용 합니다.
[CA1401](ca1401-p-invokes-should-not-be-visible.md) | P/Invoke는 노출되지 않아야 합니다.
[CA1501](ca1501-avoid-excessive-inheritance.md) | 상속성을 너무 많이 사용하지 마세요.
[CA1502](ca1502-avoid-excessive-complexity.md) | 지나치게 복잡하게 만들지 마세요.
[CA1505](ca1505-avoid-unmaintainable-code.md) | 유지 관리할 수 없는 코드를 사용하지 마세요.
[CA1506](ca1506-avoid-excessive-class-coupling.md) | 클래스를 지나치게 많이 결합하지 마세요.
[CA1507](ca1507.md) | Nameof를 사용 하 여 기호 이름을 express합니다
CA1508 | 배달 못 한 편지 조건부 코드를 방지 합니다.
CA1509 | 코드 메트릭 규칙 사양 파일의 잘못 된 항목
[CA1707](ca1707-identifiers-should-not-contain-underscores.md) | 식별자에는 밑줄을 사용할 수 없습니다.
[CA1708](ca1708-identifiers-should-differ-by-more-than-case.md) | 식별자에는 대/소문자만 다른 이름을 사용할 수 없습니다.
[CA1710](ca1710-identifiers-should-have-correct-suffix.md) | 식별자에는 올바른 접미사를 사용해야 합니다.
[CA1711](ca1711-identifiers-should-not-have-incorrect-suffix.md) | 식별자에는 올바른 접미사를 사용해야 합니다.
[CA1712](ca1712-do-not-prefix-enum-values-with-type-name.md) | 열거형 값에 형식 이름을 접두사로 사용하지 마세요.
[CA1714](ca1714-flags-enums-should-have-plural-names.md) | 플래그 열거형에는 복수형 이름을 사용해야 합니다.
[CA1715](ca1715-identifiers-should-have-correct-prefix.md) | 식별자에는 올바른 접두사를 사용해야 합니다.
[CA1716](ca1716-identifiers-should-not-match-keywords.md) | 식별자는 키워드와 달라야 합니다.
[CA1717](ca1717-only-flagsattribute-enums-should-have-plural-names.md) | FlagsAttribute 열거형만 복수형 이름을 가질 수 있습니다.
[CA1720](ca1720-identifiers-should-not-contain-type-names.md) | 식별자 형식 이름을 포함
[CA1721](ca1721-property-names-should-not-match-get-methods.md) | 속성 이름은 Get 메서드와 달라야 합니다.
[CA1724](ca1724-type-names-should-not-match-namespaces.md) | 형식 이름은 네임 스페이스를 달라 야 합니다.
[CA1725](ca1725-parameter-names-should-match-base-declaration.md) | 매개 변수 이름은 기본 선언과 일치해야 합니다.
[CA1801](ca1801-review-unused-parameters.md) | 사용되지 않은 매개 변수를 검토하세요.
[CA1802](ca1802-use-literals-where-appropriate.md) | 리터럴을 사용 하십시오.
[CA1806](ca1806-do-not-ignore-method-results.md) | 메서드 결과를 무시하지 마세요.
[CA1810](ca1810-initialize-reference-type-static-fields-inline.md) | 참조 형식 정적 필드를 인라인으로 초기화하세요.
[CA1812](ca1812-avoid-uninstantiated-internal-classes.md) | 인스턴스화되지 않은 내부 클래스를 사용하지 마세요.
[CA1813](ca1813-avoid-unsealed-attributes.md) | 봉인되지 않은 특성을 사용하지 마세요.
[CA1814](ca1814-prefer-jagged-arrays-over-multidimensional.md) | 다차원 배열보다 가변 배열을 사용하세요.
[CA1815](ca1815-override-equals-and-operator-equals-on-value-types.md) | 값 형식에서 Equals 또는 같음 연산자를 재정의하세요.
[CA1816](ca1816-call-gc-suppressfinalize-correctly.md) | Dispose 메서드 SuppressFinalize를 호출 해야 합니다.
[CA1819](ca1819-properties-should-not-return-arrays.md) | 속성은 배열을 반환해서는 안 됩니다.
[CA1820](ca1820-test-for-empty-strings-using-string-length.md) | 문자열 길이를 사용하여 빈 문자열을 테스트하세요.
[CA1821](ca1821-remove-empty-finalizers.md) | 빈 종료자를 제거 합니다.
[CA1822](ca1822-mark-members-as-static.md) | 멤버를 static으로 표시하세요.
[CA1823](ca1823-avoid-unused-private-fields.md) | 사용되지 않는 전용 필드를 사용하지 마세요.
[CA1824](ca1824-mark-assemblies-with-neutralresourceslanguageattribute.md) | NeutralResourcesLanguageAttribute로 어셈블리를 표시하세요.
CA1825 | 길이가 0 인 배열을 할당 하지 마세요.
CA1826 | 인덱싱할 수 있는 컬렉션에는 Enumerable 메서드를 사용 하지 마세요. 대신 컬렉션을 직접 사용
[CA2000](ca2000-dispose-objects-before-losing-scope.md) | 범위를 벗어나기 전에 개체를 삭제하세요.
[CA2002](ca2002-do-not-lock-on-objects-with-weak-identity.md) | 약한 ID를 가진 개체를 잠그지 마십시오.
[CA2007](ca2007-do-not-directly-await-task.md) | 대기 중인된 작업에서 ConfigureAwait를 호출 하는 것이 좋습니다.
CA2008 | TaskScheduler를 전달 하지 않고 작업을 만들지 마십시오
CA2009 | ToImmutableCollection ImmutableCollection 값에 호출 하지 마세요
CA2010 | 항상 PreserveSigAttribute로 표시 하는 메서드에서 반환 되는 값을 사용
[CA2100](ca2100-review-sql-queries-for-security-vulnerabilities.md) | 보안상 취약한 부분이 있는지 SQL 쿼리를 검토하십시오.
[CA2101](ca2101-specify-marshaling-for-p-invoke-string-arguments.md) | P/Invoke 문자열 인수에 대해 마샬링을 지정하십시오.
[CA2119](ca2119-seal-methods-that-satisfy-private-interfaces.md) | private 인터페이스를 만족하는 메서드를 봉인하세요.
[CA2153](ca2153-avoid-handling-corrupted-state-exceptions.md) | 손상 된 상태 예외를 Catch 하지 않습니다
[CA2200](ca2200-rethrow-to-preserve-stack-details.md) | 스택 정보를 유지 하도록 다시 throw 합니다.
[CA2201](ca2201-do-not-raise-reserved-exception-types.md) | 예약된 예외 형식을 발생시키지 마세요.
[CA2207](ca2207-initialize-value-type-static-fields-inline.md) | 값 형식 정적 필드 인라인을 초기화하십시오.
[CA2208](ca2208-instantiate-argument-exceptions-correctly.md) | 인수 예외를 올바르게 인스턴스화하세요.
[CA2211](ca2211-non-constant-fields-should-not-be-visible.md) | 비상수 필드는 노출되면 안 됩니다.
[CA2213](ca2213-disposable-fields-should-be-disposed.md) | 삭제 가능한 필드는 삭제해야 합니다.
[CA2214](ca2214-do-not-call-overridable-methods-in-constructors.md) | 재정의 가능한 메서드를 생성자에서 호출하지 마십시오.
[CA2216](ca2216-disposable-types-should-declare-finalizer.md) | 삭제 가능한 형식은 종료자를 선언해야 합니다.
[CA2217](ca2217-do-not-mark-enums-with-flagsattribute.md) | 열거형을 FlagsAttribute로 표시하지 마세요.
[CA2218](ca2218-override-gethashcode-on-overriding-equals.md) | Equals를 재정할 때 GetHashCode를 재정의하세요.
[CA2219](ca2219-do-not-raise-exceptions-in-exception-clauses.md) | Finally 절에서 예외를 발생 하지 않습니다
[CA2224](ca2224-override-equals-on-overloading-operator-equals.md) | Equals 오버 로드 연산자를 재정의 같음
[CA2225](ca2225-operator-overloads-have-named-alternates.md) | 연산자 오버로드에는 명명된 대체 항목이 있습니다.
[CA2226](ca2226-operators-should-have-symmetrical-overloads.md) | 연산자에는 대칭 오버로드가 있어야 합니다.
[CA2227](ca2227-collection-properties-should-be-read-only.md) | 컬렉션 속성은 읽기 전용이어야 합니다.
[CA2229](ca2229-implement-serialization-constructors.md) | serialization 생성자를 구현하십시오.
[CA2231](ca2231-overload-operator-equals-on-overriding-valuetype-equals.md) | 재정의 값에 같음 연산자를 오버 등호를 입력 합니다.
[CA2234](ca2234-pass-system-uri-objects-instead-of-strings.md) | 시스템 문자열 대신 개체를 uri 전달
[CA2235](ca2235-mark-all-non-serializable-fields.md) | 모두 serialize할 수 없는 필드로 표시하십시오.
[CA2237](ca2237-mark-iserializable-types-with-serializableattribute.md) | ISerializable 형식을 serializable로 표시하세요.
[CA2241](ca2241-provide-correct-arguments-to-formatting-methods.md) | 서식 지정 메서드에 올바른 인수를 제공하십시오.
[CA2242](ca2242-test-for-nan-correctly.md) | NaN에 대해 정확하게 테스트하십시오.
[CA2243](ca2243-attribute-string-literals-should-parse-correctly.md) | 특성 문자열 리터럴이 올바르게 구문 분석되어야 합니다.
CA2244 | 인덱싱된 요소의 초기화가 중복 되지 않는
[CA2300](ca2300-do-not-use-insecure-deserializer-binaryformatter.md) | 안전하지 않은 역직렬 변환기 BinaryFormatter를 사용하지 마세요.
[CA2301](ca2301-do-not-call-binaryformatter-deserialize-without-first-setting-binaryformatter-binder.md) | 먼저 BinaryFormatter.Binder를 설정하지 않고 BinaryFormatter.Deserialize를 호출하지 마세요.
[CA2302](ca2302-ensure-binaryformatter-binder-is-set-before-calling-binaryformatter-deserialize.md) | BinaryFormatter.Deserialize를 호출하기 전에 BinaryFormatter.Binder가 설정되었는지 확인합니다.
[CA2305](ca2305-do-not-use-insecure-deserializer-losformatter.md) | 안전하지 않은 역직렬 변환기 LosFormatter를 사용하지 마세요.
[CA2310](ca2310-do-not-use-insecure-deserializer-netdatacontractserializer.md) | 안전하지 않은 역직렬 변환기 NetDataContractSerializer를 사용하지 마세요.
[CA2311](ca2311-do-not-deserialize-without-first-setting-netdatacontractserializer-binder.md) | 먼저 NetDataContractSerializer.Binder를 설정하지 않고 deserialize하지 마세요.
[CA2312](ca2312-ensure-netdatacontractserializer-binder-is-set-before-deserializing.md) | deserialize하기 전에 NetDataContractSerializer.Binder를 설정해야 합니다.
[CA2315](ca2315-do-not-use-insecure-deserializer-objectstateformatter.md) | 안전하지 않은 역직렬 변환기 ObjectStateFormatter를 사용하지 마세요.
[CA2321](ca2321.md) | SimpleTypeResolver를 사용하여 JavaScriptSerializer를 통해 deserialize하지 마세요.
[CA2322](ca2322.md) | JavaScriptSerializer가 deserialize하기 전에 SimpleTypeResolver로 초기화되지 않는지 확인하세요.
[CA3001](ca3001-review-code-for-sql-injection-vulnerabilities.md) | 코드에서 SQL 주입 취약점에 대해 검토합니다.
[CA3002](ca3002-review-code-for-xss-vulnerabilities.md) | 코드에서 XSS 취약점에 대해 검토합니다.
[CA3003](ca3003-review-code-for-file-path-injection-vulnerabilities.md) | 코드에서 파일 경로 삽입 취약성에 대해 검토합니다.
[CA3004](ca3004-review-code-for-information-disclosure-vulnerabilities.md) | 코드에서 정보 공개 취약성에 대해 검토합니다.
[CA3005](ca3005-review-code-for-ldap-injection-vulnerabilities.md) | 코드에서 LDAP 주입 취약점에 대해 검토합니다.
[CA3006](ca3006-review-code-for-process-command-injection-vulnerabilities.md) | 코드에서 프로세스 명령 주입 취약점에 대해 검토합니다.
[CA3007](ca3007-review-code-for-open-redirect-vulnerabilities.md) | 코드에서 오픈 리디렉션 취약점에 대해 검토합니다.
[CA3008](ca3008-review-code-for-xpath-injection-vulnerabilities.md) | 코드에서 XPath 삽입 취약성에 대해 검토합니다.
[CA3009](ca3009-review-code-for-xml-injection-vulnerabilities.md) | 코드에서 XML 삽입 취약성에 대해 검토합니다.
[CA3010](ca3010-review-code-for-xaml-injection-vulnerabilities.md) | 코드에서 XAML 삽입 취약성에 대해 검토합니다.
[CA3011](ca3011-review-code-for-dll-injection-vulnerabilities.md) | 코드에서 DLL 삽입 취약성에 대해 검토합니다.
[CA3012](ca3012-review-code-for-regex-injection-vulnerabilities.md) | 코드에서 regex 삽입 취약성에 대해 검토합니다.
CA3061 | URL에서 스키마를 추가 하지 마세요
[CA3075](ca3075-insecure-dtd-processing.md) | XML의 안전하지 않은 DTD 처리
[CA3076](ca3076-insecure-xslt-script-execution.md) | 안전 하지 않은 XSLT 스크립트 처리 합니다.
[CA3077](ca3077-insecure-processing-in-api-design-xml-document-and-xml-text-reader.md) | API 디자인, XmlDocument 및 XmlTextReader에서 안전 하지 않은 처리
[CA3147](ca3147-mark-verb-handlers-with-validateantiforgerytoken.md) | 표시 동사 처리기 위조 방지 토큰 유효성 검사
[CA5350](ca5350-do-not-use-weak-cryptographic-algorithms.md) | 취약한 암호화 알고리즘을 사용하지 마세요.
[CA5351](ca5351-do-not-use-broken-cryptographic-algorithms.md) | 끊어진된 암호화 알고리즘 사용 안 함
CA5358 | 안전 하지 않은 암호화 모드를 사용 하지 마세요
CA5359 | 인증서 유효성 검사를 해제 하지 마세요
CA5360 | Deserialization에 위험한 메서드를 호출 하지 마십시오
CA5361 | SChannel 강력한 암호화 사용 안
CA5362 | 참조 하지 자체에서 Serializable 클래스
CA5363 | 요청 유효성 검사를 해제 하지 마세요
CA5364 | 사용 되지 않는 보안 프로토콜을 사용 하지 마세요
CA5365 | HTTP 헤더 확인을 해제 하지 마세요
CA5366 | XmlReader를 사용 하 여 데이터 집합 읽기 Xml
CA5367 | 형식 포인터 필드를 사용 하 여 직렬화 하지 않습니다
CA5368 | ViewStateUserKey 페이지에서 파생 된 클래스에 대 한 설정
CA5369 | XmlReader를 사용 하 여 역직렬화에 대 한
CA5370 | XmlReader를 사용 하 여 유효성 검사 판독기에 대 한
CA5371 | XmlReader를 사용 하 여 스키마 읽기
CA5372 | XmlReader를 사용 하 여 XPathDocument에 대 한
CA5373 | 사용 되지 않는 키 파생 함수를 사용 하지 마세요
CA5374 | XslTransform를 사용 하지 마세요
CA5375 | 계정 공유 액세스 서명을 사용 하지 마세요
CA5376 | SharedAccessProtocol HttpsOnly 사용
CA5377 | 컨테이너 수준 액세스 정책을 사용 하 여
CA5378 | ServicePointManagerSecurityProtocols 안
CA5379 | Weak 키 파생 함수 알고리즘을 사용 하지 마십시오
CA9999 | 분석기 버전이 일치 하지 않습니다.

> [!NOTE]
> 규칙 CA1052 및 원래 FxCop 구현과에서 CA1053 FxCop 분석기에서 단일 규칙을 CA1052로 결합 됩니다.

## <a name="unported-rules"></a>Unported 규칙

로 이식 되었으며 않은 규칙 집합이 [FxCop 분석기](install-fxcop-analyzers.md) 하지만 아직 하는 규칙으로 구성 됩니다 [이식할 수 있습니다](#rules-that-may-be-ported), 및 사용 되지 않는 및 [가져올된수없습니다](#deprecated-rules).

### <a name="rules-that-may-be-ported"></a>이식할 수 있습니다 하는 규칙

다음 FxCop 정적 코드 분석 규칙 분석기로 아직 구현 하지 않지만 여전히 수 있습니다. 이 수 또는 간단 하 게 차단 기술적인 이유 때문 규칙 더 낮은 우선 순위는 있습니다. 각 규칙의 포팅 상태에 대 한 자세한 내용은 링크를 클릭 합니다 **문제를 추적** 열입니다.

규칙 ID | 문제를 추적합니다.
--- | ---
[CA1002](ca1002-do-not-expose-generic-lists.md) | [https://github.com/dotnet/roslyn-analyzers/issues/369](https://github.com/dotnet/roslyn-analyzers/issues/369)
[CA1004](ca1004-generic-methods-should-provide-type-parameter.md) | [https://github.com/dotnet/roslyn-analyzers/issues/370](https://github.com/dotnet/roslyn-analyzers/issues/370)
[CA1005](ca1005-avoid-excessive-parameters-on-generic-types.md) | [https://github.com/dotnet/roslyn-analyzers/issues/371](https://github.com/dotnet/roslyn-analyzers/issues/371)
[CA1006](ca1006-do-not-nest-generic-types-in-member-signatures.md) | [https://github.com/dotnet/roslyn-analyzers/issues/372](https://github.com/dotnet/roslyn-analyzers/issues/372)
[CA1007](ca1007-use-generics-where-appropriate.md) | [https://github.com/dotnet/roslyn-analyzers/issues/373](https://github.com/dotnet/roslyn-analyzers/issues/373)
[CA1011](ca1011-consider-passing-base-types-as-parameters.md) | [https://github.com/dotnet/roslyn-analyzers/issues/375](https://github.com/dotnet/roslyn-analyzers/issues/375)
[CA1021](ca1021-avoid-out-parameters.md) | [https://github.com/dotnet/roslyn-analyzers/issues/377](https://github.com/dotnet/roslyn-analyzers/issues/377)
[CA1023](ca1023-indexers-should-not-be-multidimensional.md) | [https://github.com/dotnet/roslyn-analyzers/issues/378](https://github.com/dotnet/roslyn-analyzers/issues/378)
[CA1045](ca1045-do-not-pass-types-by-reference.md) | [https://github.com/dotnet/roslyn-analyzers/issues/391](https://github.com/dotnet/roslyn-analyzers/issues/391)
[CA1046](ca1046-do-not-overload-operator-equals-on-reference-types.md) | [https://github.com/dotnet/roslyn-analyzers/issues/392](https://github.com/dotnet/roslyn-analyzers/issues/392)
[CA1047](ca1047-do-not-declare-protected-members-in-sealed-types.md) | [https://github.com/dotnet/roslyn-analyzers/issues/393](https://github.com/dotnet/roslyn-analyzers/issues/393)
[CA1048](ca1048-do-not-declare-virtual-members-in-sealed-types.md) | [https://github.com/dotnet/roslyn-analyzers/issues/394](https://github.com/dotnet/roslyn-analyzers/issues/394)
[CA1049](ca1049-types-that-own-native-resources-should-be-disposable.md) | [https://github.com/dotnet/roslyn-analyzers/issues/395](https://github.com/dotnet/roslyn-analyzers/issues/395)
[CA1057](ca1057-string-uri-overloads-call-system-uri-overloads.md) | [https://github.com/dotnet/roslyn-analyzers/issues/401](https://github.com/dotnet/roslyn-analyzers/issues/401)
[CA1300](ca1300-specify-messageboxoptions.md) | [https://github.com/dotnet/roslyn-analyzers/issues/408](https://github.com/dotnet/roslyn-analyzers/issues/408)
[CA1301](ca1301-avoid-duplicate-accelerators.md) | [https://github.com/dotnet/roslyn-analyzers/issues/409](https://github.com/dotnet/roslyn-analyzers/issues/409)
[CA1306](ca1306-set-locale-for-data-types.md) | [https://github.com/dotnet/roslyn-analyzers/issues/414](https://github.com/dotnet/roslyn-analyzers/issues/414)
[CA1402](ca1402-avoid-overloads-in-com-visible-interfaces.md) | [https://github.com/dotnet/roslyn-analyzers/issues/418](https://github.com/dotnet/roslyn-analyzers/issues/418)
[CA1403](ca1403-auto-layout-types-should-not-be-com-visible.md) | [https://github.com/dotnet/roslyn-analyzers/issues/419](https://github.com/dotnet/roslyn-analyzers/issues/419)
[CA1404](ca1404-call-getlasterror-immediately-after-p-invoke.md) | [https://github.com/dotnet/roslyn-analyzers/issues/420](https://github.com/dotnet/roslyn-analyzers/issues/420)
[CA1405](ca1405-com-visible-type-base-types-should-be-com-visible.md) | [https://github.com/dotnet/roslyn-analyzers/issues/421](https://github.com/dotnet/roslyn-analyzers/issues/421)
[CA1407](ca1407-avoid-static-members-in-com-visible-types.md) | [https://github.com/dotnet/roslyn-analyzers/issues/423](https://github.com/dotnet/roslyn-analyzers/issues/423)
[CA1408](ca1408-do-not-use-autodual-classinterfacetype.md) | [https://github.com/dotnet/roslyn-analyzers/issues/424](https://github.com/dotnet/roslyn-analyzers/issues/424)
[CA1409](ca1409-com-visible-types-should-be-creatable.md) | [https://github.com/dotnet/roslyn-analyzers/issues/425](https://github.com/dotnet/roslyn-analyzers/issues/425)
[CA1410](ca1410-com-registration-methods-should-be-matched.md) | [https://github.com/dotnet/roslyn-analyzers/issues/426](https://github.com/dotnet/roslyn-analyzers/issues/426)
[CA1411](ca1411-com-registration-methods-should-not-be-visible.md) | [https://github.com/dotnet/roslyn-analyzers/issues/427](https://github.com/dotnet/roslyn-analyzers/issues/427)
[CA1412](ca1412-mark-comsource-interfaces-as-idispatch.md) | [https://github.com/dotnet/roslyn-analyzers/issues/428](https://github.com/dotnet/roslyn-analyzers/issues/428)
[CA1413](ca1413-avoid-non-public-fields-in-com-visible-value-types.md) | [https://github.com/dotnet/roslyn-analyzers/issues/429](https://github.com/dotnet/roslyn-analyzers/issues/429)
[CA1414](ca1414-mark-boolean-p-invoke-arguments-with-marshalas.md) | [https://github.com/dotnet/roslyn-analyzers/issues/430](https://github.com/dotnet/roslyn-analyzers/issues/430)
[CA1415](ca1415-declare-p-invokes-correctly.md) | [https://github.com/dotnet/roslyn-analyzers/issues/431](https://github.com/dotnet/roslyn-analyzers/issues/431)
[CA1500](ca1500-variable-names-should-not-match-field-names.md) | [https://github.com/dotnet/roslyn-analyzers/issues/432](https://github.com/dotnet/roslyn-analyzers/issues/432)
[CA1600](ca1600-do-not-use-idle-process-priority.md) | [https://github.com/dotnet/roslyn-analyzers/issues/438](https://github.com/dotnet/roslyn-analyzers/issues/438)
[CA1601](ca1601-do-not-use-timers-that-prevent-power-state-changes.md) | [https://github.com/dotnet/roslyn-analyzers/issues/439](https://github.com/dotnet/roslyn-analyzers/issues/439)
[CA1700](ca1700-do-not-name-enum-values-reserved.md) | [https://github.com/dotnet/roslyn-analyzers/issues/440](https://github.com/dotnet/roslyn-analyzers/issues/440)
[CA1704](ca1704-identifiers-should-be-spelled-correctly.md) | [https://github.com/dotnet/roslyn-analyzers/issues/443](https://github.com/dotnet/roslyn-analyzers/issues/443)
[CA1709](ca1709-identifiers-should-be-cased-correctly.md) | [https://github.com/dotnet/roslyn-analyzers/issues/445](https://github.com/dotnet/roslyn-analyzers/issues/445)
[CA1713](ca1713-events-should-not-have-before-or-after-prefix.md) | [https://github.com/dotnet/roslyn-analyzers/issues/449](https://github.com/dotnet/roslyn-analyzers/issues/449)
[CA1719](ca1719-parameter-names-should-not-match-member-names.md) | [https://github.com/dotnet/roslyn-analyzers/issues/453](https://github.com/dotnet/roslyn-analyzers/issues/453)
[CA1722](ca1722-identifiers-should-not-have-incorrect-prefix.md) | [https://github.com/dotnet/roslyn-analyzers/issues/455](https://github.com/dotnet/roslyn-analyzers/issues/455)
[CA1726](ca1726-use-preferred-terms.md) | [https://github.com/dotnet/roslyn-analyzers/issues/458](https://github.com/dotnet/roslyn-analyzers/issues/458)
[CA1804](ca1804-remove-unused-locals.md) | [https://github.com/dotnet/roslyn-analyzers/issues/461](https://github.com/dotnet/roslyn-analyzers/issues/461)
[CA1811](ca1811-avoid-uncalled-private-code.md) | [https://github.com/dotnet/roslyn-analyzers/issues/464](https://github.com/dotnet/roslyn-analyzers/issues/464)
[CA1900](ca1900-value-type-fields-should-be-portable.md) | [https://github.com/dotnet/roslyn-analyzers/issues/474](https://github.com/dotnet/roslyn-analyzers/issues/474)
[CA2001](ca2001-avoid-calling-problematic-methods.md) | [https://github.com/dotnet/roslyn-analyzers/issues/477](https://github.com/dotnet/roslyn-analyzers/issues/477)
[CA2004](ca2004-remove-calls-to-gc-keepalive.md) | [https://github.com/dotnet/roslyn-analyzers/issues/479](https://github.com/dotnet/roslyn-analyzers/issues/479)
[CA2006](ca2006-use-safehandle-to-encapsulate-native-resources.md) | [https://github.com/dotnet/roslyn-analyzers/issues/480](https://github.com/dotnet/roslyn-analyzers/issues/480)
[CA2109](ca2109-review-visible-event-handlers.md) | [https://github.com/dotnet/roslyn-analyzers/issues/488](https://github.com/dotnet/roslyn-analyzers/issues/488)
[CA2204](ca2204-literals-should-be-spelled-correctly.md) | [https://github.com/dotnet/roslyn-analyzers/issues/529](https://github.com/dotnet/roslyn-analyzers/issues/529)
[CA2205](ca2205-use-managed-equivalents-of-win32-api.md) | [https://github.com/dotnet/roslyn-analyzers/issues/530](https://github.com/dotnet/roslyn-analyzers/issues/530)
[CA2212](ca2212-do-not-mark-serviced-components-with-webmethod.md) | [https://github.com/dotnet/roslyn-analyzers/issues/534](https://github.com/dotnet/roslyn-analyzers/issues/534)
[CA2215](ca2215-dispose-methods-should-call-base-class-dispose.md) | [https://github.com/dotnet/roslyn-analyzers/issues/535](https://github.com/dotnet/roslyn-analyzers/issues/535)
[CA2232](ca2232-mark-windows-forms-entry-points-with-stathread.md) | [https://github.com/dotnet/roslyn-analyzers/issues/545](https://github.com/dotnet/roslyn-analyzers/issues/545)
[CA2236](ca2236-call-base-class-methods-on-iserializable-types.md) | [https://github.com/dotnet/roslyn-analyzers/issues/548](https://github.com/dotnet/roslyn-analyzers/issues/548)
[CA2238](ca2238-implement-serialization-methods-correctly.md) | [https://github.com/dotnet/roslyn-analyzers/issues/549](https://github.com/dotnet/roslyn-analyzers/issues/549)
[CA2239](ca2239-provide-deserialization-methods-for-optional-fields.md) | [https://github.com/dotnet/roslyn-analyzers/issues/550](https://github.com/dotnet/roslyn-analyzers/issues/550)
[CA2240](ca2240-implement-iserializable-correctly.md) | [https://github.com/dotnet/roslyn-analyzers/issues/551](https://github.com/dotnet/roslyn-analyzers/issues/551)

### <a name="deprecated-rules"></a>사용 되지 않는 규칙

다음 FxCop 정적 코드 분석 규칙은 사용 되지 않으며 분석기로 구현할 수 없습니다. 자세한 내용은 규칙 ID로 검색할 수 있습니다 (예를 들어 **CA1009**)에 [roslyn 분석기 GitHub 문제 페이지](https://github.com/dotnet/roslyn-analyzers/issues?utf8=%E2%9C%93&q=is:issue+label:FxCop-Port)합니다.

- [CA1009](ca1009-declare-event-handlers-correctly.md)
- [CA1020](ca1020-avoid-namespaces-with-few-types.md)
- [CA1025](ca1025-replace-repetitive-arguments-with-params-array.md)
- [CA1026](ca1026-default-parameters-should-not-be-used.md)
- [CA1035](ca1035-icollection-implementations-have-strongly-typed-members.md)
- [CA1038](ca1038-enumerators-should-be-strongly-typed.md)
- [CA1039](ca1039-lists-are-strongly-typed.md)
- [CA1059](ca1059-members-should-not-expose-certain-concrete-types.md)
- [CA1302](ca1302-do-not-hardcode-locale-specific-strings.md)
- [CA1400](ca1400-p-invoke-entry-points-should-exist.md)
- [CA1406](ca1406-avoid-int64-arguments-for-visual-basic-6-clients.md)
- [CA1504](ca1504-review-misleading-field-names.md)
- [CA1701](ca1701-resource-string-compound-words-should-be-cased-correctly.md)
- [CA1702](ca1702-compound-words-should-be-cased-correctly.md)
- [CA1703](ca1703-resource-strings-should-be-spelled-correctly.md)
- [CA1800](ca1800-do-not-cast-unnecessarily.md)
- [CA1809](ca1809-avoid-excessive-locals.md)
- [CA1901](ca1901-p-invoke-declarations-should-be-portable.md)
- [CA1903](ca1903-use-only-api-from-targeted-framework.md)
- [CA2003](ca2003-do-not-treat-fibers-as-threads.md)
- [CA2102](ca2102-catch-non-clscompliant-exceptions-in-general-handlers.md)
- [CA2103](ca2103-review-imperative-security.md)
- [CA2104](ca2104-do-not-declare-read-only-mutable-reference-types.md)
- [CA2105](ca2105-array-fields-should-not-be-read-only.md)
- [CA2106](ca2106-secure-asserts.md)
- [CA2107](ca2107-review-deny-and-permit-only-usage.md)
- [CA2108](ca2108-review-declarative-security-on-value-types.md)
- [CA2111](ca2111-pointers-should-not-be-visible.md)
- [CA2112](ca2112-secured-types-should-not-expose-fields.md)
- [CA2114](ca2114-method-security-should-be-a-superset-of-type.md)
- [CA2115](ca2115-call-gc-keepalive-when-using-native-resources.md)
- [CA2116](ca2116-aptca-methods-should-only-call-aptca-methods.md)
- [CA2117](ca2117-aptca-types-should-only-extend-aptca-base-types.md)
- [CA2118](ca2118-review-suppressunmanagedcodesecurityattribute-usage.md)
- [CA2120](ca2120-secure-serialization-constructors.md)
- [CA2121](ca2121-static-constructors-should-be-private.md)
- [CA2122](ca2122-do-not-indirectly-expose-methods-with-link-demands.md)
- [CA2123](ca2123-override-link-demands-should-be-identical-to-base.md)
- [CA2124](ca2124-wrap-vulnerable-finally-clauses-in-outer-try.md)
- [CA2126](ca2126-type-link-demands-require-inheritance-demands.md)
- [CA2130](ca2130-security-critical-constants-should-be-transparent.md)
- [CA2131](ca2131-security-critical-types-may-not-participate-in-type-equivalence.md)
- [CA2132](ca2132-default-constructors-must-be-at-least-as-critical-as-base-type-default-constructors.md)
- [CA2133](ca2133-delegates-must-bind-to-methods-with-consistent-transparency.md)
- [CA2134](ca2134-methods-must-keep-consistent-transparency-when-overriding-base-methods.md)
- [CA2135](ca2135-level-2-assemblies-should-not-contain-linkdemands.md)
- [CA2136](ca2136-members-should-not-have-conflicting-transparency-annotations.md)
- [CA2137](ca2137-transparent-methods-must-contain-only-verifiable-il.md)
- [CA2138](ca2138-transparent-methods-must-not-call-methods-with-the-suppressunmanagedcodesecurity-attribute.md)
- [CA2139](ca2139-transparent-methods-may-not-use-the-handleprocesscorruptingexceptions-attribute.md)
- [CA2140](ca2140-transparent-code-must-not-reference-security-critical-items.md)
- [CA2141](ca2141-transparent-methods-must-not-satisfy-linkdemands.md)
- [CA2142](ca2142-transparent-code-should-not-be-protected-with-linkdemands.md)
- [CA2143](ca2143-transparent-methods-should-not-use-security-demands.md)
- [CA2144](ca2144-transparent-code-should-not-load-assemblies-from-byte-arrays.md)
- [CA2145](ca2145-transparent-methods-should-not-be-decorated-with-the-suppressunmanagedcodesecurityattribute.md)
- [CA2146](ca2146-types-must-be-at-least-as-critical-as-their-base-types-and-interfaces.md)
- [CA2147](ca2147-transparent-methods-may-not-use-security-asserts.md)
- [CA2149](ca2149-transparent-methods-must-not-call-into-native-code.md)
- [CA2151](ca2151-fields-with-critical-types-should-be-security-critical.md)
- [CA2202](ca2202-do-not-dispose-objects-multiple-times.md)
- [CA2210](ca2210-assemblies-should-have-valid-strong-names.md)
- [CA2220](ca2220-finalizers-should-call-base-class-finalizer.md)
- [CA2221](ca2221-finalizers-should-be-protected.md)
- [CA2222](ca2222-do-not-decrease-inherited-member-visibility.md) ([근거](https://github.com/dotnet/roslyn-analyzers/issues/1378))
- [CA2223](ca2223-members-should-differ-by-more-than-return-type.md)
- [CA2228](ca2228-do-not-ship-unreleased-resource-formats.md)
- [CA2230](ca2230-use-params-for-variable-arguments.md)
- [CA2233](ca2233-operations-should-not-overflow.md)
- [CA5122](ca5122-p-invoke-declarations-should-not-be-safe-critical.md)

## <a name="see-also"></a>참고자료

- [Microsoft.CodeAnalysis.FxCopAnalyzers rules](https://github.com/dotnet/roslyn-analyzers/blob/master/src/Microsoft.CodeAnalysis.FxCopAnalyzers/Microsoft.CodeAnalysis.FxCopAnalyzers.md)