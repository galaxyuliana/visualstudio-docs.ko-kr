---
title: 관리 코드에 대한 관리 권장 규칙 규칙 집합
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 1d1160f8-4e51-4e70-99cd-82ad10ee7b32
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 2060c9c2db3dd3d60efb07b1e23c445a47d54b5d
ms.sourcegitcommit: b83fefa8177c5554cbe2c59c4d102cbc534f7cc6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2019
ms.locfileid: "69585067"
---
# <a name="managed-recommended-rules-rule-set-for-managed-code"></a>관리 코드에 대한 관리 권장 규칙 규칙 집합

Microsoft 관리 권장 규칙 규칙 집합을 사용 하 여 잠재적 보안 허점, 응용 프로그램 충돌 및 기타 중요 한 논리 및 디자인 오류를 비롯 하 여 관리 코드의 가장 중요 한 문제에 초점을 맞출 수 있습니다. 이 규칙 집합은 [관리 되는 최소 규칙](managed-minimum-rules-rule-set-for-managed-code.md) 규칙 집합의 모든 규칙을 포함 합니다.

프로젝트에 대해 만드는 모든 사용자 지정 규칙 집합에이 규칙 집합을 포함 합니다.

|규칙|Description|
|----------|-----------------|
|[CA1001](../code-quality/ca1001-types-that-own-disposable-fields-should-be-disposable.md)|삭제 가능한 필드가 있는 형식은 삭제 가능해야 합니다.|
|[CA1009](../code-quality/ca1009-declare-event-handlers-correctly.md)|이벤트 처리기를 제대로 선언하십시오.|
|[CA1016](../code-quality/ca1016-mark-assemblies-with-assemblyversionattribute.md)|AssemblyVersionAttribute로 어셈블리 표시|
|[CA1033](../code-quality/ca1033-interface-methods-should-be-callable-by-child-types.md)|인터페이스 메서드는 자식 형식에서 호출할 수 있어야 합니다.|
|[CA1049](../code-quality/ca1049-types-that-own-native-resources-should-be-disposable.md)|네이티브 리소스가 있는 형식은 삭제 가능해야 합니다.|
|[CA1060](../code-quality/ca1060-move-p-invokes-to-nativemethods-class.md)|P/Invoke를 NativeMethods 클래스로 이동|
|[CA1061](../code-quality/ca1061-do-not-hide-base-class-methods.md)|기본 클래스 메서드를 숨기지 마십시오.|
|[CA1063](../code-quality/ca1063-implement-idisposable-correctly.md)|IDisposable을 올바르게 구현하십시오.|
|[CA1065](../code-quality/ca1065-do-not-raise-exceptions-in-unexpected-locations.md)|예기치 않은 위치에서 예외를 발생시키지 마십시오.|
|[CA1301](../code-quality/ca1301-avoid-duplicate-accelerators.md)|중복 액셀러레이터 키를 사용하지 마십시오.|
|[CA1400](../code-quality/ca1400-p-invoke-entry-points-should-exist.md)|P/Invoke 진입점이 있어야 합니다.|
|[CA1401](../code-quality/ca1401-p-invokes-should-not-be-visible.md)|P/Invoke는 노출되지 않아야 합니다.|
|[CA1403](../code-quality/ca1403-auto-layout-types-should-not-be-com-visible.md)|자동 레이아웃 형식은 COM 노출이면 안 됩니다.|
|[CA1404](../code-quality/ca1404-call-getlasterror-immediately-after-p-invoke.md)|P/Invoke 다음에 바로 GetLastError를 호출하십시오.|
|[CA1405](../code-quality/ca1405-com-visible-type-base-types-should-be-com-visible.md)|COM 노출 형식의 기본 형식은 COM 노출이어야 합니다.|
|[CA1410](../code-quality/ca1410-com-registration-methods-should-be-matched.md)|COM 등록 메서드는 일치해야 합니다.|
|[CA1415](../code-quality/ca1415-declare-p-invokes-correctly.md)|P/Invoke를 올바르게 선언하십시오.|
|[CA1821](../code-quality/ca1821-remove-empty-finalizers.md)|빈 종료자를 제거하십시오.|
|[CA1900](../code-quality/ca1900-value-type-fields-should-be-portable.md)|값 형식 필드는 이식 가능해야 합니다.|
|[CA1901](../code-quality/ca1901-p-invoke-declarations-should-be-portable.md)|P/Invoke 선언은 이식 가능해야 합니다.|
|[CA2002](../code-quality/ca2002-do-not-lock-on-objects-with-weak-identity.md)|약한 ID를 가진 개체를 잠그지 마십시오.|
|[CA2100](../code-quality/ca2100-review-sql-queries-for-security-vulnerabilities.md)|보안상 취약한 부분이 있는지 SQL 쿼리를 검토하십시오.|
|[CA2101](../code-quality/ca2101-specify-marshaling-for-p-invoke-string-arguments.md)|P/Invoke 문자열 인수에 대해 마샬링을 지정하십시오.|
|[CA2108](../code-quality/ca2108-review-declarative-security-on-value-types.md)|값 형식에서 선언적 보안을 검토하십시오.|
|[CA2111](../code-quality/ca2111-pointers-should-not-be-visible.md)|포인터는 노출되면 안 됩니다.|
|[CA2112](../code-quality/ca2112-secured-types-should-not-expose-fields.md)|보안 형식은 필드를 노출하면 안 됩니다.|
|[CA2114](../code-quality/ca2114-method-security-should-be-a-superset-of-type.md)|메서드 보안은 형식의 상위 집합이어야 합니다.|
|[CA2116](../code-quality/ca2116-aptca-methods-should-only-call-aptca-methods.md)|APTCA 메서드는 APTCA 메서드만 호출해야 합니다.|
|[CA2117](../code-quality/ca2117-aptca-types-should-only-extend-aptca-base-types.md)|APTCA 형식은 APTCA 기본 형식만 확장해야 합니다.|
|[CA2122](../code-quality/ca2122-do-not-indirectly-expose-methods-with-link-demands.md)|링크 요청이 있는 메서드를 간접적으로 노출하지 마십시오.|
|[CA2123](../code-quality/ca2123-override-link-demands-should-be-identical-to-base.md)|재정의 링크 요청은 기본 링크 요청과 같아야 합니다.|
|[CA2124](../code-quality/ca2124-wrap-vulnerable-finally-clauses-in-outer-try.md)|취약한 finally 절을 외부 try에 래핑하십시오.|
|[CA2126](../code-quality/ca2126-type-link-demands-require-inheritance-demands.md)|형식 링크 요청에는 상속 요청이 필요합니다.|
|[CA2131](../code-quality/ca2131-security-critical-types-may-not-participate-in-type-equivalence.md)|보안에 중요한 형식은 형식 동등에 참여할 수 없습니다.|
|[CA2132](../code-quality/ca2132-default-constructors-must-be-at-least-as-critical-as-base-type-default-constructors.md)|기본 생성자는 기본 형식의 기본 생성자 이상으로 중요해야 합니다.|
|[CA2133](../code-quality/ca2133-delegates-must-bind-to-methods-with-consistent-transparency.md)|대리자는 투명도가 일관된 메서드에 바인딩되어야 합니다.|
|[CA2134](../code-quality/ca2134-methods-must-keep-consistent-transparency-when-overriding-base-methods.md)|메서드는 기본 메서드를 재정의할 때 일관된 투명도를 유지해야 합니다.|
|[CA2137](../code-quality/ca2137-transparent-methods-must-contain-only-verifiable-il.md)|투명 메서드에는 확인할 수 있는 IL만 포함되어야 합니다.|
|[CA2138](../code-quality/ca2138-transparent-methods-must-not-call-methods-with-the-suppressunmanagedcodesecurity-attribute.md)|투명 메서드는 SuppressUnmanagedCodeSecurity 특성을 사용하여 메서드를 호출해서는 안 됩니다.|
|[CA2140](../code-quality/ca2140-transparent-code-must-not-reference-security-critical-items.md)|투명 코드는 보안에 중요한 항목을 참조해서는 안 됩니다.|
|[CA2141](../code-quality/ca2141-transparent-methods-must-not-satisfy-linkdemands.md)|투명 메서드는 LinkDemands를 충족해서는 안 됩니다|
|[CA2146](../code-quality/ca2146-types-must-be-at-least-as-critical-as-their-base-types-and-interfaces.md)|형식은 기본 형식 및 인터페이스 이상으로 중요해야 합니다.|
|[CA2147](../code-quality/ca2147-transparent-methods-may-not-use-security-asserts.md)|투명 메서드는 보안 어설션을 사용할 수 없습니다.|
|[CA2149](../code-quality/ca2149-transparent-methods-must-not-call-into-native-code.md)|투명 메서드는 네이티브 코드를 호출해서는 안 됩니다.|
|[CA2200](../code-quality/ca2200-rethrow-to-preserve-stack-details.md)|스택 정보를 유지하도록 다시 throw하십시오.|
|[CA2202](../code-quality/ca2202-do-not-dispose-objects-multiple-times.md)|개체를 여러 번 삭제하지 마십시오.|
|[CA2207](../code-quality/ca2207-initialize-value-type-static-fields-inline.md)|값 형식 정적 필드 인라인을 초기화하십시오.|
|[CA2212](../code-quality/ca2212-do-not-mark-serviced-components-with-webmethod.md)|서비스 구성 요소를 WebMethod를 사용하여 표시하지 마십시오.|
|[CA2213](../code-quality/ca2213-disposable-fields-should-be-disposed.md)|삭제 가능한 필드는 삭제해야 합니다.|
|[CA2214](../code-quality/ca2214-do-not-call-overridable-methods-in-constructors.md)|재정의 가능한 메서드를 생성자에서 호출하지 마십시오.|
|[CA2216](../code-quality/ca2216-disposable-types-should-declare-finalizer.md)|삭제 가능한 형식은 종료자를 선언해야 합니다.|
|[CA2220](../code-quality/ca2220-finalizers-should-call-base-class-finalizer.md)|종료자는 기본 클래스 종료자를 호출해야 합니다.|
|[CA2229](../code-quality/ca2229-implement-serialization-constructors.md)|serialization 생성자를 구현하십시오.|
|[CA2231](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)|ValueType.Equals를 재정의할 때 같음 연산자를 오버로드하십시오.|
|[CA2232](../code-quality/ca2232-mark-windows-forms-entry-points-with-stathread.md)|Windows Forms 진입점을 STAThread를 사용하여 표시하십시오.|
|[CA2235](../code-quality/ca2235-mark-all-non-serializable-fields.md)|모두 serialize할 수 없는 필드로 표시하십시오.|
|[CA2236](../code-quality/ca2236-call-base-class-methods-on-iserializable-types.md)|ISerializable 형식에서 기본 클래스 메서드를 호출하십시오.|
|[CA2237](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)|SerializableAttribute로 ISerializable 형식 표시|
|[CA2238](../code-quality/ca2238-implement-serialization-methods-correctly.md)|serialization 메서드를 올바르게 구현하십시오.|
|[CA2240](../code-quality/ca2240-implement-iserializable-correctly.md)|ISerializable을 올바르게 구현하십시오.|
|[CA2241](../code-quality/ca2241-provide-correct-arguments-to-formatting-methods.md)|서식 지정 메서드에 올바른 인수를 제공하십시오.|
|[CA2242](../code-quality/ca2242-test-for-nan-correctly.md)|NaN에 대해 정확하게 테스트하십시오.|