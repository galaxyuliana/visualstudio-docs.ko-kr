---
title: 코드 분석 경고 CheckId 별 관리 코드용 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA1000
- CA1001
- CA1002
- CA1003
- CA1004
- CA1005
- CA1006
- CA1007
- CA1008
- CA1009
- CA1010
- CA1011
- CA1012
- CS1013
- CS1014
- CA1016
- CA1017
- CA1018
- CA1019
- CA1020
- CA1021
- CA1022
- CA1023
- CA1024
- CS1025
- CA1026
- CA1027
- CA1028
- CA1029
- CA1030
- CA1031
- CA1032
- CA1033
- CA1034
- CA1035
- CA1036
- CA1037
- CA1038
- CA1039
- CA1040
- CA1041
- CA1042
- CA1043
- CA1044
- CA1045
- CA1046
- CA1047
- CA1048
- CA1049
- CA1050
- CA1051
- CA1052
- CA1053
- CA1054
- CA1055
- CA1056
- CA1057
- CA1058
- CA1059
- CA1060
- CA1061
- CA1062
- CA1063
- CA1064
- CA1065
- CA1300
- CA1301
- CA1302
- CA1303
- CA1304
- CA1305
- CA1306
- CA1307
- CA1308
- CA1309
- CA1400
- CA1401
- CA1402
- CA1403
- CA1404
- CA1405
- CA1406
- CA1407
- CA1408
- CA1409
- CA1410
- CA1411
- CA1412
- CA1413
- CA1414
- CA1415
- CA1500
- CA1501
- CA1502
- CA1503
- CA1504
- CA1505
- CA1506
- CA1600
- CA1601
- CA1700
- CA1701
- CA1702
- CA1703
- CA1704
- CA1707
- CA1708
- CA1709
- CA1710
- CA1711
- CA1712
- CA1713
- CA1714
- CA1715
- VA1716
- CA1717
- CA1719
- CA1720
- CA1721
- CA1722
- CA1723
- CA1724
- CA1725
- CA1726
- CA1727
- CA1728
- CA1729
- CA1730
- CA1800
- CA1801
- CA1802
- CA1803
- CA1804
- CA1806
- CA1809
- CA1810
- CA1811
- CA1812
- CA1813
- CA1814
- CA1815
- CA1816
- CA1819
- CA1820
- CA1821
- CA1822
- CA1823
- CA1824
- CA1900
- CA1901
- CA1903
- CA2000
- CA2001
- CA2002
- CA2003
- CA2004
- CA2006
- CA2100
- CA2101
- CA2102
- CA2103
- CA2104
- CA2105
- CA2106
- CA2107
- CA2108
- CA2109
- CA2110
- CA2111
- CA2112
- CA2114
- CA2115
- CA2116
- CA2117
- CA2118
- CA2119
- CA2120
- CA2121
- CA2122
- CA2123
- CA2124
- CA2126
- CA2127
- CA2128
- CA2129
- CA2130
- CA2131
- CA2132
- CA2133
- CA2134
- CA2135
- CA2136
- CA2137
- CA2138
- CA2139
- CA2140
- CA2141
- CA2142
- CA2143
- CA2144
- CA2145
- CA2146
- CA2147
- CA2148
- CA2149
- CA2150
- CA2151
- CA2200
- CA2201
- CA2202
- CA2204
- CA2205
- CA2207
- CA2208
- CA2210
- CA2211
- CA2212
- CA2213
- CA2214
- CA2215
- CA2216
- CA2217
- CA2218
- CA2219
- CA2220
- CA2221
- CA2222
- CA2223
- CA2224
- CA2225
- CA2226
- CA2228
- CA2229
- CA2227
- CA2230
- CA2231
- CA2232
- CA2233
- CA2234
- CA2235
- CA2236
- CA2237
- CA2238
- CA2239
- CA2240
- CA2241
- CA2242
- CA2243
- CA5122
ms.assetid: 5cb221f6-dc59-4abf-9bfa-adbd6f907f96
caps.latest.revision: 23
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 91dcea4d9d16a6e846a66e4a5590dedfdc62b90f
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68201474"
---
# <a name="code-analysis-warnings-for-managed-code-by-checkid"></a>관리되는 코드에 대한 CheckId별 코드 분석 경고
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

다음 표에서는 관리 코드에 대한 코드 분석 경고를 경고의 CheckId 식별자별로 보여 줍니다.  
  
## <a name="warnings"></a>경고  
  
|CheckId|경고|설명|  
|-------------|-------------|-----------------|  
|CA1000|[CA1000: 제네릭 형식에 정적 멤버를 선언 하지 마십시오](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)|제네릭 형식의 정적 멤버를 호출할 때는 형식에 형식 인수를 지정해야 합니다. 유추를 지원하지 않는 제네릭 인스턴스 멤버를 호출할 때는 멤버에 형식 인수를 지정해야 합니다. 이 두 가지 경우에 형식 인수를 지정하기 위한 구문은 서로 다르며 혼동되기 쉽습니다.|  
|CA1001|[CA1001: 삭제 가능한 필드가 있는 형식은 삭제 가능해야 합니다.](../code-quality/ca1001-types-that-own-disposable-fields-should-be-disposable.md)|클래스가 System.IDisposable 형식인 인스턴스 필드를 선언하고 구현하지만 IDisposable은 구현하지 않습니다. IDisposable 필드를 선언하는 클래스는 관리되지 않는 리소스를 간접적으로 소유하며 IDisposable 인터페이스를 구현해야 합니다.|  
|CA1002|[CA1002: 제네릭 목록을 노출 하지 마십시오](../code-quality/ca1002-do-not-expose-generic-lists.md)|System.Collections.Generic.List < (의 \<(T >) >)는 상속이 아니라 성능을 위해 설계 된 제네릭 컬렉션입니다. 따라서 List에는 가상 멤버가 포함되지 않습니다. 상속을 위해 디자인된 제네릭 컬렉션이 대신 노출되어야 합니다.|  
|CA1003|[CA1003: 제네릭 이벤트 처리기 인스턴스를 사용 합니다.](../code-quality/ca1003-use-generic-event-handler-instances.md)|void를 반환 하며 해당 시그니처에 두 개의 매개 변수 (개체가 첫 번째 및 두 번째는 EventArgs에 할당 될 수 있는 형식)를 포함 하는 대리자를 포함 하는 형식을 포함 하는 어셈블리에는 Microsoft.NET Framework 2.0 대상으로 합니다.|  
|CA1004|[CA1004: 제네릭 메서드 형식 매개 변수를 제공 해야 합니다.](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)|제네릭 메서드의 형식 인수가 형식 인수를 명시적으로 지정하는 대신 메서드로 전달된 인수의 형식에 따라 결정되는 방식을 유추라고 합니다. 유추를 사용하려면 제네릭 메서드의 매개 변수 시그니처에 메서드에 대한 형식 매개 변수와 같은 형식의 매개 변수가 포함되어야 합니다. 이 경우 형식 인수는 지정할 필요가 없습니다. 모든 형식 매개 변수에 대해 유추를 사용하는 경우 제네릭과 제네릭이 아닌 인스턴스 메서드를 호출하는 구문은 동일합니다. 따라서 제네릭 메서드를 사용하기가 간편해집니다.|  
|CA1005|[CA1005: 제네릭 형식에 매개 변수를 방지 합니다.](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)|제네릭 형식에 포함된 형식 매개 변수가 많을수록 각 형식 매개 변수가 무엇을 나타내는지를 파악하거나 기억하기가 더 어렵습니다. 보통은 목록와 같이 하나의 형식 매개 변수를 사용 하 여\<T >에서 같이 두 개의 형식 매개 변수가 있는 경우에 특정\<TKey, TValue >. 그러나 형식 매개 변수가 세 개 이상이면 대부분의 사용자가 사용하기에 너무 어렵습니다.|  
|CA1006|[CA1006: 멤버 시그니처에 제네릭 형식을 중첩 하지 마십시오.](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)|중첩된 형식 인수는 제네릭 형식의 인수입니다. 시그니처에 중첩된 형식 인수가 포함되어 있는 멤버를 호출하려면 제네릭 형식 하나를 인스턴스화하고 이 형식을 두 번째 제네릭 형식의 생성자에 전달해야 합니다. 이 경우 복잡한 프로시저와 구문이 필요하므로 이 방법을 피해야 합니다.|  
|CA1007|[CA1007: 적합 한 제네릭을 사용합니다](../code-quality/ca1007-use-generics-where-appropriate.md)|외부에서 볼 수 있는 메서드에 System.Object 형식의 참조 매개 변수가 포함되어 있습니다. 제네릭 메서드를 사용하면 제약 조건에 따라 형식을 참조 매개 변수 형식으로 먼저 캐스팅하지 않고도 모든 형식을 메서드에 전달할 수 있습니다.|  
|CA1008|[CA1008: 열거형 값이 0 이면 있어야 합니다.](../code-quality/ca1008-enums-should-have-zero-value.md)|초기화되지 않은 열거형의 기본값은 다른 값 형식과 마찬가지로 0입니다. 플래그 특성을 사용하지 않는 열거형에서는 기본값이 열거형의 유효한 값이 되도록 0 값을 사용하여 멤버를 정의해야 합니다. FlagsAttribute 특성이 적용된 열거형에서 0 값을 가진 멤버를 정의하는 경우에는 열거형에 값이 설정되지 않았음을 나타낼 수 있도록 해당 멤버 이름이 "None"이어야 합니다.|  
|CA1009|[CA1009: 이벤트 처리기를 제대로 선언 하십시오.](../code-quality/ca1009-declare-event-handlers-correctly.md)|이벤트 처리기 메서드는 두 개의 매개 변수를 사용합니다. 첫 번째 매개 변수는 System.Object 형식이고 이름은 "sender"입니다. 이 매개 변수는 이벤트를 발생시킨 개체입니다. 두 번째 매개 변수는 System.EventArgs 형식이고 이름은 "e"입니다. 이 매개 변수는 이벤트와 관련된 데이터입니다. 이벤트 처리기 메서드는 값을 반환하지 않아야 하며, C# 프로그래밍 언어에서 이는 반환 형식 void로 표시됩니다.|  
|CA1010|[CA1010: 컬렉션에서 제네릭 인터페이스를 구현 해야 합니다.](../code-quality/ca1010-collections-should-implement-generic-interface.md)|컬렉션의 유용성을 높이려면 제네릭 컬렉션 인터페이스 중 하나를 구현합니다. 그러면 컬렉션을 사용하여 제네릭 컬렉션 형식을 채울 수 있습니다.|  
|CA1011|[CA1011: 기본 형식을 매개 변수로 전달 하는 것이 좋습니다.](../code-quality/ca1011-consider-passing-base-types-as-parameters.md)|기본 형식이 메서드 선언의 매개 변수로 지정된 경우 기본 형식에서 파생된 모든 형식을 해당 인수로 메서드에 전달할 수 있습니다. 파생된 매개 변수 형식에서 제공하는 추가 기능이 필요하지 않은 경우 기본 형식을 사용하면 메서드를 보다 광범위하게 사용할 수 있습니다.|  
|CA1012|[CA1012: 추상 형식에는 생성자를 사용 해야 합니다.](../code-quality/ca1012-abstract-types-should-not-have-constructors.md)|추상 형식에 대한 생성자는 파생된 형식에서만 호출할 수 있습니다. public 생성자에서 형식의 인스턴스를 만들고 사용자는 추상 형식의 인스턴스를 만들 수 없기 때문에 public 생성자가 있는 추상 형식은 잘못 디자인된 것입니다.|  
|CA1013|[CA1013: 오버 로드에 같음 연산자를 오버 더하기 및 빼기](../code-quality/ca1013-overload-operator-equals-on-overloading-add-and-subtract.md)|public 또는 protected 형식이 같음 연산자를 구현하지 않고 더하기 또는 빼기 연산자를 구현합니다.|  
|CA1014|[CA1014: CLSCompliantAttribute로 어셈블리 표시](../code-quality/ca1014-mark-assemblies-with-clscompliantattribute.md)|CLS(공용 언어 사양)는 어셈블리가 여러 프로그래밍 언어에 사용될 경우 준수해야 하는 명명 제한, 데이터 형식 및 규칙을 정의합니다. 모든 어셈블리에는 <xref:System.CLSCompliantAttribute>를 사용하여 CLS 규격을 명시적으로 나타내는 것이 좋습니다. 어셈블리에 이 특성이 없으면 해당 어셈블리는 규격을 따르지 않습니다.|  
|CA1016|[CA1016: AssemblyVersionAttribute로 어셈블리 표시](../code-quality/ca1016-mark-assemblies-with-assemblyversionattribute.md)|[!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]에서는 버전 번호를 사용하여 어셈블리를 고유하게 식별하고 강력한 이름이 지정된 어셈블리의 형식에 바인딩합니다. 버전 번호는 버전 및 게시자 정책과 함께 사용됩니다. 기본적으로 애플리케이션은 해당 애플리케이션이 빌드될 때 사용된 어셈블리 버전으로만 실행됩니다.|  
|CA1017|[CA1017: ComVisibleAttribute로 어셈블리 표시](../code-quality/ca1017-mark-assemblies-with-comvisibleattribute.md)|ComVisibleAttribute는 COM 클라이언트에서 관리 코드에 액세스하는 방식을 결정합니다. 어셈블리에서 COM에 노출할지 여부를 명시적으로 나타내는 것이 좋은 디자인입니다. 전체 어셈블리에 대해 COM 노출 여부를 설정한 다음 개별 형식 및 형식 멤버에 대해 이를 재정의할 수 있습니다. 이 특성이 없으면 COM 클라이언트에서 어셈블리의 내용을 볼 수 있습니다.|  
|CA1018|[CA1018: 특성을 attributeusageattribute로 표시](../code-quality/ca1018-mark-attributes-with-attributeusageattribute.md)|사용자 지정 특성을 정의할 때는 해당 특성을 AttributeUsageAttribute로 표시하여 사용자 지정 특성을 적용할 수 있는 소스 코드의 위치를 나타냅니다. 특성의 의미 및 용도에 따라 코드에서의 유효한 위치가 결정됩니다.|  
|CA1019|[CA1019: 특성 인수의 접근자를 정의 합니다.](../code-quality/ca1019-define-accessors-for-attribute-arguments.md)|특성에서는 대상에 특성을 적용할 때 지정해야 하는 필수 인수를 정의할 수 있습니다. 이러한 인수는 특성 생성자에 위치 매개 변수로 제공되기 때문에 이러한 인수를 위치 인수라고도 합니다. 모든 필수 인수에 대해 특성은 실행 시간에 인수의 값을 검색할 수 있도록 해당하는 읽기 전용 속성도 제공해야 합니다. 특성에서는 명명된 인수라고 하는 선택적 인수도 정의할 수 있습니다. 이들 인수는 이름으로 특성 생성자에 제공되며 해당하는 읽기/쓰기 특성이 있어야 합니다.|  
|CA1020|[CA1020: 몇 가지 형식과 네임 스페이스를 방지 합니다.](../code-quality/ca1020-avoid-namespaces-with-few-types.md)|각 네임스페이스에 논리적 구성이 있는지, 형식이 부족한 네임스페이스에 형식을 배치하는 타당한 근거가 있는지 확인합니다.|  
|CA1021|[CA1021: Out 매개 변수를 방지](../code-quality/ca1021-avoid-out-parameters.md)|out 또는 ref를 사용하여 참조로 형식을 전달하려면 포인터 사용 방법을 알고 있어야 하고, 값 형식과 참조 형식이 어떻게 다른지 알고 있어야 하며, 반환 값이 여러 개인 메서드를 처리할 수 있어야 합니다. 또한 out 매개 변수와 ref 매개 변수의 차이점은 잘 알려져 있지 않습니다.|  
|CA1023|[CA1023: 다차원 인덱서 설정 되지 않습니다.](../code-quality/ca1023-indexers-should-not-be-multidimensional.md)|인덱서, 즉 인덱싱된 속성은 단일 인덱스를 사용해야 합니다. 다차원 인덱서를 사용하면 라이브러리의 유용성이 현저히 줄어들 수 있습니다.|  
|CA1024|[CA1024: 적절 한 속성을 사용 합니다.](../code-quality/ca1024-use-properties-where-appropriate.md)|public 또는 protected 메서드가 "Get"으로 시작하는 이름을 사용하고, 매개 변수를 사용하지 않으며, 배열이 아닌 값을 반환합니다. 이 메서드는 속성이 될 수 있는 좋은 예일 수 있습니다.|  
|CA1025|[CA1025: 반복 인수를 배열로 바꾸십시오.](../code-quality/ca1025-replace-repetitive-arguments-with-params-array.md)|인수의 정확한 개수를 알 수 없는데 가변 인수가 같은 형식이거나 같은 형식으로서 전달될 수 있는 경우에는 반복되는 인수 대신 매개 변수 배열을 사용합니다.|  
|CA1026|[CA1026: 기본 매개 변수를 사용 하지 않아야](../code-quality/ca1026-default-parameters-should-not-be-used.md)|CLS에서는 기본 매개 변수를 사용하는 메서드를 허용하지만 컴파일러가 이러한 매개 변수에 할당된 값을 무시할 수 있도록 합니다. 여러 프로그래밍 언어에서 원하는 동작을 유지하려면 기본 매개 변수를 사용하는 메서드를 기본 매개 변수를 제공하는 메서드 오버로드로 바꿔야 합니다.|  
|CA1027|[CA1027: 열거형을 FlagsAttribute로 표시](../code-quality/ca1027-mark-enums-with-flagsattribute.md)|열거형은 서로 관련 있는 명명된 상수 집합을 정의하는 값 형식입니다. 명명된 상수를 의미 있게 조합할 수 있는 경우 열거형에 FlagsAttribute를 적용합니다.|  
|CA1028|[CA1028: 열거형 저장소는 Int32 여야 합니다.](../code-quality/ca1028-enum-storage-should-be-int32.md)|열거형은 서로 관련 있는 명명된 상수 집합을 정의하는 값 형식입니다. 기본적으로 System.Int32 데이터 형식은 상수 값을 저장하는 데 사용됩니다. 이 내부 형식을 변경할 수 있지만 대부분의 시나리오에서는 변경이 필요하지 않거나 권장되지 않습니다.|  
|CA1030|[CA1030: 적절 한 이벤트를 사용 합니다.](../code-quality/ca1030-use-events-where-appropriate.md)|이 규칙에서는 보통 이벤트에 사용되는 이름을 갖는 메서드를 찾아냅니다. 명확하게 정의된 상태 변경에 대한 응답으로 메서드를 호출할 경우 이 메서드는 이벤트 처리기에서 호출해야 합니다. 메서드를 호출하는 개체는 메서드를 직접 호출하는 대신 이벤트를 발생시켜야 합니다.|  
|CA1031|[CA1031: 일반적인 예외 형식을 catch 하지 마십시오.](../code-quality/ca1031-do-not-catch-general-exception-types.md)|일반 예외는 catch하면 안 됩니다. 보다 구체적인 예외를 catch하거나, 일반적인 예외를 catch 블록의 마지막 문으로 다시 throw해야 합니다.|  
|CA1032|[CA1032: 표준 예외 생성자를 구현 합니다.](../code-quality/ca1032-implement-standard-exception-constructors.md)|이들 생성자 집합을 전부 제공하지 못하면 예외를 제대로 처리하기 어려울 수 있습니다.|  
|CA1033|[CA1033: 인터페이스 메서드는 자식 형식에서 호출할 수 있어야 합니다.](../code-quality/ca1033-interface-methods-should-be-callable-by-child-types.md)|외부에서 볼 수 있는 unsealed 형식이 public 인터페이스의 명시적 메서드 구현을 제공하면서 외부에서 볼 수 있는 같은 이름의 대체 메서드를 제공하지 않습니다.|  
|CA1034|[CA1034: 중첩된 형식은 표시 해야 합니다.](../code-quality/ca1034-nested-types-should-not-be-visible.md)|중첩 형식은 다른 형식의 범위 내에 선언된 형식입니다. 중첩 형식은 포함하는 형식의 private 구현 정보를 캡슐화하는 데 유용합니다. 이 용도로 사용할 경우 중첩 형식은 외부에 노출되면 안 됩니다.|  
|CA1035|[CA1035: ICollection 구현에 강력한 형식의 멤버가](../code-quality/ca1035-icollection-implementations-have-strongly-typed-members.md)|이 규칙에서는 사용자가 인터페이스에서 제공하는 기능을 사용할 때 인수를 Object 형식으로 캐스팅할 필요가 없도록 ICollection 구현에서 강력한 형식의 멤버를 제공할 것을 요구합니다. 이 규칙에서는 ICollection을 구현하는 형식이 이를 수행하여 Object보다 강력한 형식의 인스턴스 컬렉션을 관리한다고 가정합니다.|  
|CA1036|[CA1036: 비교 가능한 형식에 메서드를 재정의 합니다.](../code-quality/ca1036-override-methods-on-comparable-types.md)|public 또는 protected 형식이 System.IComparable 인터페이스를 구현합니다. 이 형식은 Object.Equals를 재정의하지 않으며 같음, 같지 않음, 보다 작음 또는 보다 큼에 대한 언어별 연산자를 오버로드하지 않습니다.|  
|CA1038|[CA1038: 열거자는 강력한 형식 이어야 합니다.](../code-quality/ca1038-enumerators-should-be-strongly-typed.md)|이 규칙에서는 사용자가 인터페이스에서 제공하는 기능을 사용할 때 반환 값을 강력한 형식으로 캐스팅할 필요가 없도록 IEnumerator 구현에서 Current 속성의 강력한 형식 버전도 제공할 것을 요구합니다.|  
|CA1039|[CA1039: 목록은 강력한 형식](../code-quality/ca1039-lists-are-strongly-typed.md)|이 규칙에서는 사용자가 인터페이스에서 제공하는 기능을 사용할 때 인수를 System.Object 형식으로 캐스팅할 필요가 없도록 IList 구현에서 강력한 형식의 멤버를 제공할 것을 요구합니다.|  
|CA1040|[CA1040: 빈 인터페이스 방지](../code-quality/ca1040-avoid-empty-interfaces.md)|인터페이스에서는 동작이나 사용 계약을 제공하는 멤버를 정의합니다. 인터페이스에 의해 설명되는 기능은 상속 계층 구조에서 형식이 나타나는 위치에 관계없이 모든 형식에서 사용할 수 있습니다. 형식에서는 인터페이스의 멤버에 대한 구현을 제공하여 인터페이스를 구현합니다. 빈 인터페이스는 멤버를 정의하지 않으므로 구현 가능한 계약을 정의하지 않습니다.|  
|CA1041|[CA1041: ObsoleteAttribute 메시지를 제공 합니다.](../code-quality/ca1041-provide-obsoleteattribute-message.md)|형식 또는 멤버가 ObsoleteAttribute.Message 속성이 지정되지 않은 System.ObsoleteAttribute 특성으로 표시되어 있습니다. ObsoleteAttribute로 표시된 형식 또는 멤버를 컴파일하면 해당 특성의 Message 속성이 표시되어 사용되지 않는 형식 또는 멤버에 대한 정보가 사용자에게 제공됩니다.|  
|CA1043|[CA1043: 인덱서에 정수 또는 문자열 인수를 사용 하 여](../code-quality/ca1043-use-integral-or-string-argument-for-indexers.md)|인덱서, 즉 인덱싱된 속성은 인덱스에 정수 계열 형식이나 문자열 형식을 사용해야 합니다. 이러한 형식은 대개 데이터 구조를 인덱싱하는 데 사용되며 라이브러리의 유용성을 증가시킵니다. Object 형식은 디자인 타임에 특정 정수 계열 형식이나 문자열 형식을 지정할 수 없는 경우에만 제한적으로 사용해야 합니다.|  
|CA1044|[CA1044: 속성에는 쓰기 전용를 사용 해야 합니다.](../code-quality/ca1044-properties-should-not-be-write-only.md)|읽기 전용 속성을 사용하는 것은 가능하고 종종 필요하기도 하지만 쓰기 전용 속성의 사용은 금지되어 있습니다. 사용자에게 값을 설정하도록 허용한 다음 해당 값을 볼 수 없도록 하면 보안상 문제가 있기 때문입니다. 또한 읽기 권한이 없으면 공유 개체의 상태를 볼 수 없으므로 사용하는 데 제한을 받습니다.|  
|CA1045|[CA1045: 참조로 형식을 전달 하지 않습니다](../code-quality/ca1045-do-not-pass-types-by-reference.md)|out 또는 ref를 사용하여 참조로 형식을 전달하려면 포인터 사용 방법을 알고 있어야 하고, 값 형식과 참조 형식이 어떻게 다른지 알고 있어야 하며, 반환 값이 여러 개인 메서드를 처리할 수 있어야 합니다. 일반 사용자를 대상으로 디자인하는 라이브러리 설계자는 사용자가 out 또는 ref 매개 변수를 사용하는 작업에 능숙할 것이라고 기대해서는 안 됩니다.|  
|CA1046|[CA1046: 참조 형식에 같음 연산자 오버 로드 하지 마십시오.](../code-quality/ca1046-do-not-overload-operator-equals-on-reference-types.md)|참조 형식의 경우 같음 연산자의 기본 구현은 대부분 항상 올바릅니다. 기본적으로 두 참조는 같은 개체를 가리킬 경우에만 같습니다.|  
|CA1047|[CA1047: 보호 된 멤버를 sealed 형식 선언 하지 마십시오](../code-quality/ca1047-do-not-declare-protected-members-in-sealed-types.md)|형식에서는 상속하는 형식에서 멤버에 액세스하거나 멤버를 재정의할 수 있도록 하기 위해 protected 멤버를 선언합니다. 정의에 따라 sealed 형식은 상속할 수 없으므로 sealed 형식에 대해 protected 메서드를 호출할 수 없습니다.|  
|CA1048|[CA1048: 가상 멤버를 sealed 형식 선언 하지 마십시오](../code-quality/ca1048-do-not-declare-virtual-members-in-sealed-types.md)|상속 형식이 가상 메서드의 구현을 재정의할 수 있도록 하기 위해 형식은 메서드를 가상으로 선언합니다. 정의에 따라 sealed 형식은 상속할 수 없습니다. 따라서 sealed 형식에 대한 가상 메서드는 의미가 없습니다.|  
|CA1049|[CA1049: 네이티브 리소스가 있는 형식은 삭제 가능 해야 합니다.](../code-quality/ca1049-types-that-own-native-resources-should-be-disposable.md)|관리되지 않는 리소스를 할당하는 형식은 IDisposable을 구현하여 호출자가 필요할 때 해당 리소스를 해제할 수 있도록 하고 리소스를 차지하고 있는 개체의 수명을 줄여야 합니다.|  
|CA1050|[CA1050: 네임 스페이스의 형식을 선언 하십시오.](../code-quality/ca1050-declare-types-in-namespaces.md)|이름 충돌을 방지하고 관련된 형식을 개체 계층 구조로 구성하기 위해 형식은 네임스페이스 안에 선언됩니다.|  
|CA1051|[CA1051: 표시 되는 인스턴스 필드 선언 하지 마십시오.](../code-quality/ca1051-do-not-declare-visible-instance-fields.md)|필드의 주된 용도는 구현을 세부적으로 설명하는 것입니다. 필드는 private 또는 internal이어야 하고 속성을 통해 노출되어야 합니다.|  
|CA1052|[CA1052: 정적 소유자 형식은 sealed 여야 합니다.](../code-quality/ca1052-static-holder-types-should-be-sealed.md)|public 또는 protected 형식이 정적 멤버만 포함하며 sealed(C# 참조)(NotInheritable) 한정자로 선언되지 않았습니다. 상속을 고려하지 않은 형식은 sealed 한정자로 표시하여 기본 형식으로 사용되지 않도록 해야 합니다.|  
|CA1053|[CA1053: 정적 소유자 형식에는 생성자를 사용 해야 합니다.](../code-quality/ca1053-static-holder-types-should-not-have-constructors.md)|public 또는 중첩된 public 형식에서 정적 멤버만 선언하며 public 또는 protected 기본 생성자를 사용합니다. 호출하는 정적 멤버에 형식의 인스턴스가 필요하지 않기 때문에 생성자가 필요 없습니다. 문자열 오버로드는 안전과 보안을 위해 문자열 인수를 사용하여 URI(Uniform Resource Identifier) 오버로드를 호출해야 합니다.|  
|CA1054|[CA1054: URI 매개 변수는 문자열이 면 안 됩니다.](../code-quality/ca1054-uri-parameters-should-not-be-strings.md)|메서드가 URI의 문자열 표현을 사용하면 URI 클래스의 인스턴스를 사용하는 해당 오버로드를 제공해야 합니다. 이렇게 하면 서비스가 안전한 방식으로 제공됩니다.|  
|CA1055|[CA1055: URI 반환 값은 문자열이 면 안 됩니다.](../code-quality/ca1055-uri-return-values-should-not-be-strings.md)|이 규칙에서는 메서드가 URI를 반환한다고 가정합니다. URI의 문자열 표현은 구문 분석 및 인코딩 오류를 발생시키기 쉬우며 보안 문제를 일으킬 수 있습니다. System.Uri 클래스는 이러한 서비스를 안전한 방식으로 제공합니다.|  
|CA1056|[CA1056: URI 속성은 문자열이 면 안 됩니다.](../code-quality/ca1056-uri-properties-should-not-be-strings.md)|이 규칙에서는 속성이 URI(Uniform Resource Identifier)를 나타낸다고 가정합니다. URI의 문자열 표현은 구문 분석 및 인코딩 오류를 발생시키기 쉬우며 보안 문제를 일으킬 수 있습니다. System.Uri 클래스는 이러한 서비스를 안전한 방식으로 제공합니다.|  
|CA1057|[CA1057: 문자열 URI 오버 로드는 System.Uri 오버 로드를 호출](../code-quality/ca1057-string-uri-overloads-call-system-uri-overloads.md)|형식에서 문자열 매개 변수가 System.Uri 매개 변수로 바뀐 점만 다른 메서드 오버로드를 선언합니다. 문자열 매개 변수를 사용하는 오버로드는 URI 매개 변수를 사용하는 오버로드를 호출하지 않습니다.|  
|CA1058|[CA1058: 형식은 특정 기본 형식을 확장하면 안 됩니다.](../code-quality/ca1058-types-should-not-extend-certain-base-types.md)|외부에서 볼 수 있는 형식이 특정 기본 형식을 확장합니다. 다음 방법 중 하나를 사용합니다.|  
|CA1059|[CA1059: 멤버는 구체적인 특정 형식을 노출 해야](../code-quality/ca1059-members-should-not-expose-certain-concrete-types.md)|구체적인 형식은 완전히 구현되었기 때문에 인스턴스화할 수 있는 형식을 말합니다. 멤버를 광범위하게 사용할 수 있도록 하려면 구체적인 형식을 제안된 인터페이스로 바꾸십시오.|  
|CA1060|[CA1060: P/Invoke를 NativeMethods 클래스로 이동](../code-quality/ca1060-move-p-invokes-to-nativemethods-class.md)|System.Runtime.InteropServices.DllImportAttribute 특성으로 표시된 메서드나 [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]에서 Declare 키워드를 사용하여 정의된 메서드 같은 플랫폼 호출 메서드에서는 비관리 코드에 액세스합니다. 이러한 메서드는 NativeMethods, SafeNativeMethods 또는 UnsafeNativeMethods 클래스에 속해야 합니다.|  
|CA1061|[CA1061: 기본 클래스 메서드를 숨기지 않음](../code-quality/ca1061-do-not-hide-base-class-methods.md)|파생된 메서드의 매개 변수 시그니처가 기본 메서드의 매개 변수 시그니처에 있는 해당 형식보다 더 약하게 파생된 형식이라는 점만 다른 경우 기본 형식의 메서드는 파생된 형식에 있는 동일한 이름의 메서드에 의해 숨겨집니다.|  
|CA1062|[CA1062: Public 메서드의 인수의 유효성을 검사합니다](../code-quality/ca1062-validate-arguments-of-public-methods.md)|외부에서 볼 수 있는 메서드에 전달되는 모든 참조 인수는 null인지 여부를 검사해야 합니다.|  
|CA1063|[CA1063: IDisposable을 올바르게 구현](../code-quality/ca1063-implement-idisposable-correctly.md)|모든 IDisposable 형식은 Dispose 패턴을 올바르게 구현해야 합니다.|  
|CA1064|[CA1064: 예외는 public 이어야 합니다.](../code-quality/ca1064-exceptions-should-be-public.md)|내부 예외는 내부 범위 내에만 표시됩니다. 예외가 내부 범위 밖에 놓이게 되면 예외를 catch하는 데 기본 예외만 사용할 수 있습니다. T:System.Exception, T:System.SystemException, T:System.ApplicationException에서 내부 예외가 상속되는 경우 외부 코드에는 예외를 사용하여 수행할 수 있는 내용에 대한 충분한 정보가 없게 됩니다.|  
|CA1065|[CA1065: 예기치 않은 위치에서 예외를 발생 하지 않습니다](../code-quality/ca1065-do-not-raise-exceptions-in-unexpected-locations.md)|예외를 throw하지 않아야 하는 메서드가 예외를 throw했습니다.|  
|CA1300|[CA1300: MessageBoxOptions를 지정 합니다.](../code-quality/ca1300-specify-messageboxoptions.md)|오른쪽에서 왼쪽으로 읽기 순서를 사용하는 문화권에 대해 메시지 상자를 올바로 표시하려면 MessageBoxOptions 열거형의 RightAlign 및 RtlReading 멤버를 Show 메서드로 전달해야 합니다.|  
|CA1301|[CA1301: 중복 액셀러레이터를 방지 합니다.](../code-quality/ca1301-avoid-duplicate-accelerators.md)|액셀러레이터 키라고도 하는 선택키를 사용하면 Alt 키를 사용하여 키보드로 컨트롤에 액세스할 수 있습니다. 여러 컨트롤에 중복되는 선택키가 있으면 선택키의 동작이 제대로 정의되지 않은 경우입니다.|  
|CA1302|[CA1302: 로캘별 문자열을 하드 코딩 하지 마십시오](../code-quality/ca1302-do-not-hardcode-locale-specific-strings.md)|System.Environment.SpecialFolder 열거형에는 특수 시스템 폴더를 참조하는 멤버가 포함되어 있습니다. 이러한 폴더의 위치는 운영 체제에 따라 값이 다를 수 있으며, 사용자가 위치 일부를 변경할 수 있고, 위치는 지역화됩니다. Environment.GetFolderPath 메서드는 Environment.SpecialFolder 열거형과 연관된 위치를 반환하며 이 위치는 지역화되므로 현재 실행되고 있는 컴퓨터에 적합합니다.|  
|CA1303|[CA1303: 리터럴을 지역화 된 매개 변수로 전달 하지 마십시오](../code-quality/ca1303-do-not-pass-literals-as-localized-parameters.md)|외부에서 볼 수 있는 메서드가 [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] 클래스 라이브러리의 생성자 또는 메서드에 문자열 리터럴을 매개 변수로 전달하는데 이 문자열은 지역화될 수 있어야 합니다.|  
|CA1304|[CA1304: CultureInfo를 지정 합니다.](../code-quality/ca1304-specify-cultureinfo.md)|메서드 또는 생성자가 System.Globalization.CultureInfo 매개 변수를 받아들이는 오버로드가 있는 멤버를 호출하지만 CultureInfo 매개 변수를 사용하는 오버로드는 호출하지 않습니다. CultureInfo 또는 System.IFormatProvider 개체가 제공되지 않으면 오버로드된 멤버에서 제공하는 기본값이 모든 로캘에서 원하는 효과를 나타내지 않을 수 있습니다.|  
|CA1305|[CA1305: IFormatProvider를 지정 합니다.](../code-quality/ca1305-specify-iformatprovider.md)|메서드 또는 생성자가 System.IFormatProvider 매개 변수를 받아들이는 오버로드가 있는 하나 이상의 멤버를 호출하지만 IFormatProvider 매개 변수를 사용하는 오버로드는 호출하지 않습니다. System.Globalization.CultureInfo 또는 IFormatProvider 개체가 제공되지 않으면 오버로드된 멤버에서 제공하는 기본값이 모든 로캘에서 원하는 효과를 나타내지 않을 수 있습니다.|  
|CA1306|[CA1306: 데이터 형식에 대 한 로캘을 설정 하십시오.](../code-quality/ca1306-set-locale-for-data-types.md)|로캘은 숫자 값에 사용되는 서식, 통화 기호 및 정렬 순서 등과 같은 데이터의 문화권별 표현 요소를 결정합니다. DataTable 또는 DataSet를 만들 때는 로캘을 명시적으로 설정해야 합니다.|  
|CA1307|[CA1307: StringComparison 지정](../code-quality/ca1307-specify-stringcomparison.md)|문자열 비교 작업에서 StringComparison 매개 변수를 설정하지 않는 메서드 오버로드를 사용합니다.|  
|CA1308|[CA1308: 문자열을 대문자로 정규화 하십시오.](../code-quality/ca1308-normalize-strings-to-uppercase.md)|문자열은 대문자로 정규화되어야 합니다. 일부 문자는 소문자로 변환될 때 다시 대문자로 변환될 수 없습니다.|  
|CA1309|[CA1309: 서 수 StringComparison 사용](../code-quality/ca1309-use-ordinal-stringcomparison.md)|비언어 문자열 비교 작업에서는 StringComparison 매개 변수를 Ordinal 또는 OrdinalIgnoreCase로 설정하지 않습니다. 매개 변수가 명시적으로 StringComparison.Ordinal 또는 StringComparison.OrdinalIgnoreCase로 설정되기 때문에 코드 실행 속도, 정확도 및 신뢰도가 향상됩니다.|  
|CA1400|[CA1400: P/Invoke 진입점 있어야 합니다.](../code-quality/ca1400-p-invoke-entry-points-should-exist.md)|public 또는 protected 메서드는 System.Runtime.InteropServices.DllImportAttribute 특성으로 표시됩니다. 관리되지 않는 라이브러리를 찾을 수 없거나 해당 메서드와 라이브러리의 함수가 일치하지 않습니다.|  
|CA1401|[CA1401: P/Invoke을 표시 해야 합니다.](../code-quality/ca1401-p-invokes-should-not-be-visible.md)|public 형식의 public 또는 protected 메서드는 System.Runtime.InteropServices.DllImportAttribute 특성을 가지며 또한 [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]에서 Declare 키워드로 구현됩니다. 이러한 메서드는 노출되지 않아야 합니다.|  
|CA1402|[CA1402: COM 노출 인터페이스에서 오버 로드 방지](../code-quality/ca1402-avoid-overloads-in-com-visible-interfaces.md)|오버로드된 메서드가 COM 클라이언트에 노출되면 첫 번째 메서드 오버로드만 이름이 유지됩니다. 이후의 오버로드는 이름에 밑줄 문자(_)와 오버로드 선언 순서에 해당하는 정수가 추가되어 고유한 이름이 지정됩니다.|  
|CA1403|[CA1403: 자동 레이아웃 형식은 com 노출 이면 안](../code-quality/ca1403-auto-layout-types-should-not-be-com-visible.md)|COM 노출 값 형식이 LayoutKind.Auto로 설정된 System.Runtime.InteropServices.StructLayoutAttribute 특성을 사용하여 표시되어 있습니다. 이러한 형식의 레이아웃은 [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] 버전 간에 변경될 수 있으므로 특정 레이아웃이 필요한 COM 클라이언트에서는 문제가 발생할 수 있습니다.|  
|CA1404|[CA1404: P/Invoke 다음에 바로 GetLastError를 호출 합니다.](../code-quality/ca1404-call-getlasterror-immediately-after-p-invoke.md)|Marshal.GetLastWin32Error 메서드 또는 해당 호출 [!INCLUDE[TLA2#tla_win32](../includes/tla2sharptla-win32-md.md)] GetLastError 함수를 하 고 즉시 이전 호출은 운영 체제 아닌 메서드를 호출 합니다.|  
|CA1405|[CA1405: COM 노출 형식의 기본 형식은 COM 노출 해야 합니다.](../code-quality/ca1405-com-visible-type-base-types-should-be-com-visible.md)|COM 노출 형식이 COM에 노출되지 않는 형식에서 파생됩니다.|  
|CA1406|[CA1406: Visual Basic 6 클라이언트에서 Int64 인수를 방지 합니다.](../code-quality/ca1406-avoid-int64-arguments-for-visual-basic-6-clients.md)|Visual Basic 6 COM 클라이언트는 64 비트 정수를 액세스할 수 없습니다.|  
|CA1407|[CA1407: COM 노출 형식에 정적 멤버를 방지 합니다.](../code-quality/ca1407-avoid-static-members-in-com-visible-types.md)|COM에서는 static 메서드를 지원하지 않습니다.|  
|CA1408|[CA1408: AutoDual ClassInterfaceType을 사용 하지 마십시오](../code-quality/ca1408-do-not-use-autodual-classinterfacetype.md)|이중 인터페이스를 사용하는 형식에서는 클라이언트가 특정 인터페이스 레이아웃에 바인딩할 수 있습니다. 이후 버전에서 해당 형식이나 기본 형식의 레이아웃이 변경되면 인터페이스에 바인딩된 COM 클라이언트의 바인딩이 해제될 수 있습니다. 기본적으로 ClassInterfaceAttribute 특성이 지정되어 있지 않으면 디스패치 전용 인터페이스가 사용됩니다.|  
|CA1409|[CA1409: Com 노출 형식을 만들 수 있어야 합니다.](../code-quality/ca1409-com-visible-types-should-be-creatable.md)|COM에 표시되는 것으로 특별히 표시된 참조 형식에 매개 변수가 있는 public 생성자가 있지만 매개 변수가 없는 public 기본 생성자가 없습니다. COM 클라이언트에서는 public 기본 생성자가 없는 형식을 만들 수 없습니다.|  
|CA1410|[CA1410: COM 등록 메서드는 일치 해야 합니다.](../code-quality/ca1410-com-registration-methods-should-be-matched.md)|형식이 System.Runtime.InteropServices.ComRegisterFunctionAttribute 특성으로 표시된 메서드를 선언하지만 System.Runtime.InteropServices.ComUnregisterFunctionAttribute 특성으로 표시된 메서드는 선언하지 않거나 그 반대의 경우입니다.|  
|CA1411|[CA1411: COM 등록 메서드를 표시 해야 합니다.](../code-quality/ca1411-com-registration-methods-should-not-be-visible.md)|System.Runtime.InteropServices.ComRegisterFunctionAttribute 특성 또는 System.Runtime.InteropServices.ComUnregisterFunctionAttribute 특성으로 표시된 메서드가 외부에 노출됩니다.|  
|CA1412|[CA1412: ComSource 인터페이스 IDispatch로 표시](../code-quality/ca1412-mark-comsource-interfaces-as-idispatch.md)|형식이 System.Runtime.InteropServices.ComSourceInterfacesAttribute 특성으로 표시되어 있으며 지정된 인터페이스 중 하나 이상이 ComInterfaceType.InterfaceIsIDispatch로 설정된 System.Runtime.InteropServices.InterfaceTypeAttribute 특성으로 표시되어 있지 않습니다.|  
|CA1413|[CA1413: COM 노출 값 형식에 public이 아닌 필드를 방지 합니다.](../code-quality/ca1413-avoid-non-public-fields-in-com-visible-value-types.md)|public이 아니며 값 형식이 COM에 노출되는 인스턴스 필드는 COM 클라이언트에서 볼 수 있습니다. 필드의 내용을 검토하여 노출되지 않아야 하거나 디자인 또는 보안에 의도하지 않은 영향을 줄 수 있는 정보가 있는지 확인합니다.|  
|CA1414|[CA1414: 부울 P/Invoke 인수를 marshalas로 표시](../code-quality/ca1414-mark-boolean-p-invoke-arguments-with-marshalas.md)|부울 데이터 형식은 비관리 코드에서 여러 가지로 표현됩니다.|  
|CA1415|[CA1415: P/Invoke를 올바르게 선언 하십시오.](../code-quality/ca1415-declare-p-invokes-correctly.md)|이 규칙에서는 OVERLAPPED 구조체 매개 변수에 대한 포인터가 있는 [!INCLUDE[TLA2#tla_win32](../includes/tla2sharptla-win32-md.md)] 함수를 대상으로 하는 운영 체제 호출 메서드 선언을 찾는데 관리되는 해당 매개 변수가 System.Threading.NativeOverlapped 구조체에 대한 포인터가 아닙니다.|  
|CA1500|[CA1500: 변수 이름은 필드 이름과 일치 하지는](../code-quality/ca1500-variable-names-should-not-match-field-names.md)|인스턴스 메서드에서 선언 형식의 인스턴스 필드와 이름이 같은 매개 변수나 지역 변수를 선언합니다. 이로 인해 오류가 발생합니다.|  
|CA1501|[CA1501: 과도 한 상속을 방지](../code-quality/ca1501-avoid-excessive-inheritance.md)|형식이 상속 계층 구조에서 네 단계보다 아래에 있습니다. 여러 번 중첩된 형식 계층 구조는 추적하고, 이해하고, 유지 관리하기가 어렵습니다.|  
|CA1502|[CA1502: 과도 한 복잡성을 방지 합니다.](../code-quality/ca1502-avoid-excessive-complexity.md)|이 규칙은 메서드를 통과하는 선형 독립 경로의 수를 측정하며 조건부 분기의 수와 복잡성에 의해 결정됩니다.|  
|CA1504|[CA1504: 잘못 된 필드 이름을 검토 하십시오.](../code-quality/ca1504-review-misleading-field-names.md)|인스턴스 필드의 이름이 "s_"로 시작 하거나 정적 (Visual Basic에서는 Shared) 필드의 이름이 "m_"로 시작 합니다.|  
|CA1505|[CA1505: 유지 관리할 수 없는 코드를 방지 합니다.](../code-quality/ca1505-avoid-unmaintainable-code.md)|형식 또는 메서드에 낮은 유지 관리 인덱스 값이 있습니다. 낮은 유지 관리 인덱스는 형식 또는 메서드가 유지 관리하기 어렵고 다시 디자인될 수 있음을 나타냅니다.|  
|CA1506|[CA1506: 클래스 결합을 방지](../code-quality/ca1506-avoid-excessive-class-coupling.md)|이 규칙은 형식 또는 메서드에 들어 있는 고유한 형식 참조의 개수를 계산하여 클래스 결합을 측정합니다.|  
|CA1600|[CA1600: 유휴 프로세스 우선 순위를 사용 하지 마세요](../code-quality/ca1600-do-not-use-idle-process-priority.md)|프로세스 우선 순위를 유휴 상태로 설정하지 마십시오. System.Diagnostics.ProcessPriorityClass.Idle인 프로세스는 어떠한 이유로든 유휴 상태가 될 경우 CPU를 차지하므로 블록이 대기 모드가 됩니다.|  
|CA1601|[CA1601: 전원 상태 변경을 방해 하는 타이머를 사용 하지 마십시오](../code-quality/ca1601-do-not-use-timers-that-prevent-power-state-changes.md)|정기적인 작업의 실행 빈도가 높아지면 CPU 사용률도 높아져 디스플레이 및 하드 디스크를 끄는 절전 유휴 타이머에 방해가 됩니다.|  
|CA1700|[CA1700: 열거형 값 ' 이름을 바꾸지 마십시오](../code-quality/ca1700-do-not-name-enum-values-reserved.md)|이 규칙에서는 "reserved"라는 단어가 포함된 이름을 갖는 열거형 멤버가 현재 사용되지는 않지만 이후 버전에서 이름이 바뀌거나 제거될 자리 표시자라고 가정합니다. 멤버의 이름을 바꾸거나 멤버를 제거하는 것은 주요 변경에 해당합니다.|  
|CA1701|[CA1701: 리소스 문자열 복합 단어에는 올바르게 표기를 사용 해야](../code-quality/ca1701-resource-string-compound-words-should-be-cased-correctly.md)|리소스 문자열의 각 단어는 대/소문자에 따라 토큰으로 구분됩니다. Microsoft 맞춤법 검사 라이브러리에서는 연속된 각 두 토큰의 조합을 검사합니다. 규칙 위반이 인식되면 단어에서 규칙 위반을 작성합니다.|  
|CA1702|[CA1702: 복합 단어에는 올바르게 표기를 사용 해야](../code-quality/ca1702-compound-words-should-be-cased-correctly.md)|식별자 이름에 여러 개의 단어가 포함되어 있으며 이 중 적어도 하나의 단어가 대/소문자를 정확하게 사용하지 않은 복합 단어인 것 같습니다.|  
|CA1703|[CA1703: 리소스 문자열에는 정확한 철자를 사용 해야](../code-quality/ca1703-resource-strings-should-be-spelled-correctly.md)|리소스 문자열에 Microsoft 맞춤법 검사 라이브러리에서 인식하지 못하는 단어가 하나 이상 있습니다.|  
|CA1704|[CA1704: 식별자에는 정확한 철자를 사용 해야](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md)|외부에서 볼 수 있는 식별자의 이름에 Microsoft 맞춤법 검사 라이브러리에서 인식하지 못하는 단어가 하나 이상 있습니다.|  
|CA1707|[CA1707: 식별자에는 밑줄 없어야 합니다.](../code-quality/ca1707-identifiers-should-not-contain-underscores.md)|규칙에 따라 식별자 이름에는 밑줄 문자(_)가 포함될 수 없습니다. 이 규칙에서는 네임스페이스, 형식, 멤버 및 매개 변수를 검사합니다.|  
|CA1708|[CA1708: 식별자 대/소문자만 달라 야 합니다.](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)|공용 언어 런타임을 대상으로 하는 언어는 대/소문자를 구분하지 않으므로 네임스페이스, 형식, 멤버 및 매개 변수의 식별자가 대/소문자만 달라서는 안 됩니다.|  
|CA1709|[CA1709: 식별자에는 올바르게 표기를 사용 해야](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)|규칙에 따라 매개 변수 이름에는 카멜식 대/소문자 구분을 사용하고 네임스페이스, 형식 및 멤버 이름에는 파스칼식 대/소문자 구분을 사용합니다.|  
|CA1710|[CA1710: 식별자에는 올바른 접미사를 사용 해야 합니다.](../code-quality/ca1710-identifiers-should-have-correct-suffix.md)|규칙에 따라 특정 기본 형식을 확장하거나 특정 인터페이스를 구현하는 형식 또는 이러한 형식에서 파생되는 형식은 이름에 기본 형식이나 인터페이스와 연관된 접미사를 갖습니다.|  
|CA1711|[CA1711: 식별자에는 접미사를 사용 해야 합니다.](../code-quality/ca1711-identifiers-should-not-have-incorrect-suffix.md)|규칙에 따라 특정 기본 형식을 확장하거나 특정 인터페이스를 구현하는 형식의 이름 또는 이러한 형식에서 파생되는 형식의 이름만이 예약된 특정 접미사로 끝나야 합니다. 다른 형식 이름에는 이러한 예약된 접미사를 사용하면 안 됩니다.|  
|CA1712|[CA1712: 열거형 값 형식 이름의 접두사로 사용 하지 마세요](../code-quality/ca1712-do-not-prefix-enum-values-with-type-name.md)|개발 도구에서 형식 정보를 제공하므로 열거형 멤버의 이름에는 형식 이름을 접두사로 사용하지 않습니다.|  
|CA1713|[CA1713: 이벤트에는 before 또는 after 접두사 없어야](../code-quality/ca1713-events-should-not-have-before-or-after-prefix.md)|이벤트 이름이 "Before" 또는 "After"로 시작합니다. 특정 시퀀스에서 발생하는 관련 이벤트의 이름을 지정하려면 현재 또는 과거 시제를 사용하여 동작 시퀀스 내의 상대적인 위치를 나타냅니다.|  
|CA1714|[CA1714: 플래그 열거형에는 복수형 이름을 사용 해야 합니다.](../code-quality/ca1714-flags-enums-should-have-plural-names.md)|public 열거형에 System.FlagsAttribute 특성이 있고 이름이 "s"로 끝나지 않았습니다. FlagsAttribute 특성은 둘 이상의 값을 지정할 수 있음을 나타내므로 이 특성으로 표시된 형식은 복수형 이름을 갖습니다.|  
|CA1715|[CA1715: 식별자에는 올바른 접두사를 사용 해야 합니다.](../code-quality/ca1715-identifiers-should-have-correct-prefix.md)|외부에 노출되는 인터페이스의 이름이 대문자 "I"로 시작하지 않습니다. 외부에 노출되는 형식 또는 메서드의 제네릭 형식 매개 변수 이름이 대문자 "T"로 시작하지 않습니다.|  
|CA1716|[CA1716: 식별자는 키워드와 일치](../code-quality/ca1716-identifiers-should-not-match-keywords.md)|네임스페이스 이름 또는 형식 이름이 프로그래밍 언어의 예약된 키워드와 일치합니다. 네임스페이스 및 형식에 대한 식별자는 공용 언어 런타임을 대상으로 하는 언어에서 정의된 키워드와 일치하면 안 됩니다.|  
|CA1717|[CA1717: FlagsAttribute 열거형만 복수형 이름이 있어야 합니다.](../code-quality/ca1717-only-flagsattribute-enums-should-have-plural-names.md)|명명 규칙은 열거형 이름이 복수형인 경우 여러 열거 값을 동시에 지정할 수 있음을 나타내도록 되어 있습니다.|  
|CA1719|[CA1719: 매개 변수 이름은 멤버 이름과 일치 하지는](../code-quality/ca1719-parameter-names-should-not-match-member-names.md)|매개 변수 이름은 매개 변수의 의미를 나타내고 멤버 이름은 멤버의 의미를 나타내야 합니다. 매개 변수와 멤버의 의미가 같게 디자인되는 경우는 드뭅니다. 매개 변수의 이름을 멤버 이름과 동일하게 지정하는 것은 비직관적이고 라이브러리 사용을 어렵게 만듭니다.|  
|CA1720|[CA1720: 식별자에 형식 이름을 포함 해야 합니다.](../code-quality/ca1720-identifiers-should-not-contain-type-names.md)|외부에 노출되는 멤버의 매개 변수 이름에 데이터 형식 이름이 포함되어 있거나 외부에 노출되는 멤버의 이름에 언어에 따라 다른 데이터 형식 이름이 포함되어 있습니다.|  
|CA1721|[CA1721: 속성 이름은 get 메서드와 달라 야 합니다.](../code-quality/ca1721-property-names-should-not-match-get-methods.md)|public 또는 protected 멤버의 이름이 "Get"으로 시작하며 이름의 나머지 부분이 public 또는 protected 속성의 이름과 같습니다. "Get" 메서드와 속성은 서로가 분명히 구분되는 이름을 사용해야 합니다.|  
|CA1722|[CA1722: 식별자에는 잘못 된 접두사를 사용 해야 합니다.](../code-quality/ca1722-identifiers-should-not-have-incorrect-prefix.md)|규칙에 따라 특정 프로그래밍 요소에만 특정 접두사로 시작하는 이름을 사용할 수 있습니다.|  
|CA1724|[CA1724: 형식 이름은 네임 스페이스 달라 야 합니다.](../code-quality/ca1724-type-names-should-not-match-namespaces.md)|형식 이름은 [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] 클래스 라이브러리에 정의된 네임스페이스의 이름과 같아서는 안 됩니다. 이 규칙을 위반하면 라이브러리의 유용성이 저하될 수 있습니다.|  
|CA1725|[CA1725: 매개 변수 이름은 기본 선언과 일치 해야 합니다.](../code-quality/ca1725-parameter-names-should-match-base-declaration.md)|재정의 계층 구조에서 매개 변수 이름을 일관되게 지정하면 메서드 재정의를 더 편리하게 사용할 수 있습니다. 파생된 메서드의 매개 변수 이름이 기본 선언의 이름과 다르면 메서드가 기본 메서드의 재정의인지 메서드의 새 오버로드인지를 혼동할 수 있습니다.|  
|CA1726|[CA1726: 기본 설정된 용어를 사용 합니다.](../code-quality/ca1726-use-preferred-terms.md)|외부에서 볼 수 있는 식별자의 이름에 특정 용어가 포함되어 있는데, 이 용어에는 기본 설정된 대체 용어가 있습니다. 또는 이름에 "Flag"나 "Flags"라는 용어가 포함되어 있습니다.|  
|CA1800|[CA1800: 불필요 하 게 캐스팅 하지 마십시오](../code-quality/ca1800-do-not-cast-unnecessarily.md)|중복 캐스팅을 수행하면 성능이 저하됩니다. 특히 간단한 반복 문에서 캐스팅이 수행될 때 더욱 그러합니다.|  
|CA1801|[CA1801: 사용 되지 않는 매개 변수를 검토](../code-quality/ca1801-review-unused-parameters.md)|메서드 시그니처에 메서드 본문에서 사용되지 않는 매개 변수가 있습니다.|  
|CA1802|[CA1802: 리터럴을 사용 하십시오.](../code-quality/ca1802-use-literals-where-appropriate.md)|필드가 static 및 read-only([!INCLUDE[vbprvb](../includes/vbprvb-md.md)]의 경우 Shared 및 ReadOnly)로 선언되었으며 컴파일할 때 계산할 수 있는 값으로 초기화되어 있습니다. 컴파일 시간에 대상된 필드에 할당 되는 값을 계산할 이기 때문에 const 선언을 변경 (에서 Const [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]) 필드 값을 런타임 대신 컴파일 시간에 계산 되도록 합니다.|  
|CA1804|[CA1804: 사용 되지 않는 로컬 항목을 제거](../code-quality/ca1804-remove-unused-locals.md)|사용되지 않는 지역 변수와 불필요한 할당으로 어셈블리의 크기가 증가하고 성능이 저하될 수 있습니다.|  
|CA1806|[CA1806: 메서드 결과 무시 하지 마십시오](../code-quality/ca1806-do-not-ignore-method-results.md)|새 개체가 만들어지지만 사용되지 않거나, 새 문자열을 만들고 반환하는 메서드가 호출되고 새 문자열이 사용되지 않거나, COM 또는 P/Invoke 메서드가 사용되지 않는 오류 코드나 HRESULT를 반환합니다.|  
|CA1809|[CA1809: 과도 한 지역 변수를 방지 합니다.](../code-quality/ca1809-avoid-excessive-locals.md)|값을 메모리가 아닌 프로세서 레지스터에 저장하는 방법은 성능 최적화에 많이 사용되는 방법이며 "값의 레지스터 등록"이라고도 합니다. 모든 지역 변수에 레지스터는 가능성을 늘리려면 64 로컬 변수 수를 제한 합니다.|  
|CA1810|[CA1810: 참조 형식 정적 필드를 인라인으로 초기화](../code-quality/ca1810-initialize-reference-type-static-fields-inline.md)|형식이 명시적인 정적 생성자를 선언하면 JIT(Just-in-Time) 컴파일러는 형식의 각 정적 메서드와 인스턴스 생성자에 검사를 추가하여 정적 생성자를 이전에 호출했는지 확인합니다. 정적 생성자 검사로 인해 성능이 저하될 수 있습니다.|  
|CA1811|[CA1811: 호출 되지 않는 전용 코드를 방지 합니다.](../code-quality/ca1811-avoid-uncalled-private-code.md)|어셈블리에 private 또는 internal(어셈블리 수준) 멤버의 호출자가 없고, 공용 언어 런타임에서도 이 멤버를 호출하지 않으며, 대리자에서도 이 멤버를 호출하지 않습니다.|  
|CA1812|[CA1812: 인스턴스화되지 않은 내부 클래스를 방지 합니다.](../code-quality/ca1812-avoid-uninstantiated-internal-classes.md)|어셈블리 수준 형식의 인스턴스가 어셈블리에서 코드에 의해 만들어지지 않습니다.|  
|CA1813|[CA1813: 봉인 되지 않은 특성](../code-quality/ca1813-avoid-unsealed-attributes.md)|[!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] 클래스 라이브러리는 사용자 지정 특성을 검색하는 메서드를 제공합니다. 기본적으로 이러한 메서드는 특성 상속 계층을 검색합니다. 특성을 봉인하면 상속 계층을 검색하지 않으므로 성능이 향상될 수 있습니다.|  
|CA1814|[CA1814: 다차원 보다 가변 배열을 사용합니다](../code-quality/ca1814-prefer-jagged-arrays-over-multidimensional.md)|가변 배열의 요소에는 배열이 사용됩니다. 요소를 구성하는 배열의 크기는 서로 다를 수 있습니다. 이 경우 일부 데이터 집합에 대한 공간을 절약할 수 있습니다.|  
|CA1815|[CA1815: 값 형식에서 Equals 또는 같음 연산자 재정의](../code-quality/ca1815-override-equals-and-operator-equals-on-value-types.md)를 참조하세요.|값 형식의 경우 Equals의 상속된 구현에서 Reflection 라이브러리를 사용하며 모든 필드의 내용을 비교합니다. Reflection에는 많은 계산이 요구되며 모든 필드의 일치 여부를 비교하는 것이 불필요할 수 있습니다. 사용자가 인스턴스를 비교 또는 정렬하거나 인스턴스를 해시 테이블 키로 사용할 것으로 예측되는 경우에는 값 형식에서 Equals를 구현해야 합니다.|  
|CA1816|[CA1816: GC를 호출 합니다. SuppressFinalize 올바르게](../code-quality/ca1816-call-gc-suppressfinalize-correctly.md)|Dispose 구현인 메서드가 GC를 호출 하지 않습니다. SuppressFinalize; 또는 Dispose 구현 되지 않는 메서드가 GC를 호출 합니다. SuppressFinalize; 또는 GC를 호출 합니다. SuppressFinalize 및 전달이 (Visual Basic의 Me) 이외의 것입니다.|  
|CA1819|[CA1819: 속성은 배열을 반환 해서는](../code-quality/ca1819-properties-should-not-return-arrays.md)|속성에서 반환된 배열은 속성이 읽기 전용이더라도 쓰기 금지되지 않습니다. 배열을 무단으로 변경하지 못하도록 하려면 속성에서 배열의 복사본을 반환해야 합니다. 일반적으로 사용자는 이러한 속성을 호출할 경우 성능에 부정적인 영향을 준다는 것을 인식하지 못합니다.|  
|CA1820|[CA1820: 문자열 길이 사용 하 여 문자열이 비었는지 테스트](../code-quality/ca1820-test-for-empty-strings-using-string-length.md)|String.Length 속성이나 String.IsNullOrEmpty 메서드를 사용하여 문자열을 비교하는 것이 Equals를 사용하는 것보다 훨씬 더 빠릅니다.|  
|CA1821|[CA1821: 빈 종료자를 제거하십시오.](../code-quality/ca1821-remove-empty-finalizers.md)|개체 수명을 추적할 때에는 추가로 성능 오버헤드가 발생하므로 가능한 경우 종료자를 사용하지 마십시오. 빈 종료자는 아무런 장점 없이 오버헤드만 가중시킵니다.|  
|CA1822|[CA1822: 멤버를 static으로 표시](../code-quality/ca1822-mark-members-as-static.md)|인스턴스 데이터에 액세스하지 않거나 인스턴스 메서드를 호출하지 않는 멤버는 static([!INCLUDE[vbprvb](../includes/vbprvb-md.md)]의 경우 Shared)으로 표시할 수 있습니다. 메서드를 static으로 표시하면 컴파일러는 이러한 멤버에 대한 비가상 호출 사이트를 내보냅니다. 이 경우 성능이 중요한 코드에서 성능이 크게 향상될 수 있습니다.|  
|CA1823|[CA1823: 사용 되지 않는 전용 필드를 방지 합니다.](../code-quality/ca1823-avoid-unused-private-fields.md)|어셈블리에서 액세스되지 않는 것으로 보이는 전용 필드가 발견되었습니다.|  
|CA1824|[CA1824: NeutralResourcesLanguageAttribute로 어셈블리 표시](../code-quality/ca1824-mark-assemblies-with-neutralresourceslanguageattribute.md)|NeutralResourcesLanguage 특성을 사용하여 어셈블리에 대한 중립 문화권의 리소스를 표시하는 데 사용된 언어를 ResourceManager에 알릴 수 있습니다. 이렇게 하면 로드한 첫 리소스에 대한 찾기 성능을 향상시킬 수 있으며 작업이 간단해집니다.|  
|CA1900|[CA1900: 값 형식 필드는 이식 가능 해야 합니다.](../code-quality/ca1900-value-type-fields-should-be-portable.md)|이 규칙에서는 명시적 레이아웃으로 선언된 구조체가 64비트 운영 체제에서 비관리 코드로 마샬링될 때 올바르게 맞춰지는지 검사합니다.|  
|CA1901|[CA1901: P/Invoke 선언은 이식 가능 해야 합니다.](../code-quality/ca1901-p-invoke-declarations-should-be-portable.md)|이 규칙은 P/Invoke의 반환 값과 각 매개 변수의 크기를 계산하여 32비트 및 64비트 운영 체제에서 비관리 코드로 마샬링될 때 해당 매개 변수의 크기가 올바른지 확인합니다.|  
|CA1903|[CA1903: 대상된 프레임 워크에서 API만 사용](../code-quality/ca1903-use-only-api-from-targeted-framework.md)|멤버 또는 형식이 프로젝트의 대상 프레임워크에 함께 포함되지 않은 서비스 팩에 도입된 멤버 또는 형식을 사용합니다.|  
|CA2000|[CA2000: 범위를 벗어나기 전에 개체를 삭제 합니다.](../code-quality/ca2000-dispose-objects-before-losing-scope.md)|개체의 종료자가 실행되지 못하도록 하는 예외 이벤트가 발생할 수 있기 때문에 개체에 대한 모든 참조가 범위를 벗어나기 전에 개체를 명시적으로 삭제해야 합니다.|  
|CA2001|[CA2001: 문제가 있는 메서드를 호출 하지 마십시오.](../code-quality/ca2001-avoid-calling-problematic-methods.md)|멤버에서 잠재적 위험이나 문제가 있는 메서드를 호출합니다.|  
|CA2002|[CA2002: 약한 id 가진 개체를 잠그지 마십시오.](../code-quality/ca2002-do-not-lock-on-objects-with-weak-identity.md)|애플리케이션 도메인 경계를 가로질러 직접 액세스할 수 있는 개체를 약한 ID를 가진 개체라고 합니다. 약한 ID를 가진 개체에 대해 잠금을 가져오려고 시도하는 스레드는 같은 개체에 대해 잠금을 가진 다른 애플리케이션 도메인의 스레드에 의해 차단될 수 있습니다.|  
|CA2003|[CA2003: 파이버를 스레드로 취급 하지 마십시오](../code-quality/ca2003-do-not-treat-fibers-as-threads.md)|관리되는 스레드가 [!INCLUDE[TLA2#tla_win32](../includes/tla2sharptla-win32-md.md)] 스레드처럼 취급됩니다.|  
|CA2004|[CA2004: GC에 대 한 호출을 제거 합니다. KeepAlive](../code-quality/ca2004-remove-calls-to-gc-keepalive.md)|SafeHandle을 사용하는 방식으로 변환하는 경우 GC.KeepAlive(개체)에 대한 모든 호출을 제거해야 합니다. 이 경우 클래스에 종료자가 없지만 SafeHandle을 사용하여 OS 핸들을 종료하는 것으로 간주하므로 클래스에서 GC.KeepAlive를 호출할 필요가 없습니다.|  
|CA2006|[CA2006: 네이티브 리소스를 캡슐화 하기 위해 SafeHandle 사용](../code-quality/ca2006-use-safehandle-to-encapsulate-native-resources.md)|관리 코드에 IntPtr을 사용하는 것은 잠재적인 보안 및 안정성 문제를 나타냅니다. IntPtr을 사용할 때마다 SafeHandle 또는 유사한 기술을 대신 사용해야 하는지 여부를 결정하도록 검토해야 합니다.|  
|CA2100|[CA2100: 보안 취약점에 대 한 SQL 쿼리를 검토 합니다.](../code-quality/ca2100-review-sql-queries-for-security-vulnerabilities.md)|메서드가 메서드에 대한 문자열 인수로부터 만들어진 문자열을 사용하여 System.Data.IDbCommand.CommandText 속성을 설정합니다. 이 규칙에서는 문자열 인수에 사용자 입력이 포함된 것으로 가정합니다. 사용자 입력으로부터 만들어진 SQL 명령 문자열은 SQL 삽입 공격에 취약합니다.|  
|CA2101|[CA2101: P/Invoke 문자열 인수에 대해 마샬링을 지정 하십시오.](../code-quality/ca2101-specify-marshaling-for-p-invoke-string-arguments.md)|플랫폼 호출 멤버가 부분 신뢰 호출자를 허용하고, 문자열 매개 변수를 사용하고, 문자열을 명시적으로 마샬링하지 않습니다. 이렇게 하면 보안상 위험할 수 있습니다.|  
|CA2102|[CA2102: 일반 처리기에서 비 CLSCompliant 예외를 catch 합니다.](../code-quality/ca2102-catch-non-clscompliant-exceptions-in-general-handlers.md)|RuntimeCompatibilityAttribute로 표시되지 않거나 RuntimeCompatibility(WrapNonExceptionThrows = false)로 표시된 어셈블리의 멤버에는 System.Exception을 처리하는 catch 블록이 포함되며 바로 뒤의 일반 catch 블록은 포함되지 않습니다.|  
|CA2103|[CA2103: 명령적 보안을 검토](../code-quality/ca2103-review-imperative-security.md)|메서드가 명령적 보안을 사용하고, 요청이 활성 상태인 동안 변경될 수 있는 반환 값 또는 상태 정보를 사용하여 권한을 구성하고 있습니다. 가능하면 선언적 보안을 사용합니다.|  
|CA2104|[CA2104: 읽기 전용 참조 형식을 선언 하지 마십시오.](../code-quality/ca2104-do-not-declare-read-only-mutable-reference-types.md)|외부에서 볼 수 있는 형식에 변경 가능한 참조 형식인, 외부에서 볼 수 있는 읽기 전용 필드가 포함되었습니다. 변경 가능한 형식은 해당 인스턴스 데이터를 수정할 수 있는 형식을 말합니다.|  
|CA2105|[CA2105: 배열 필드는 읽기 전용 이면 안](../code-quality/ca2105-array-fields-should-not-be-read-only.md)|배열이 들어 있는 필드에 read-only([!INCLUDE[vbprvb](../includes/vbprvb-md.md)]의 경우 ReadOnly) 한정자를 적용하면 필드를 변경하여 다른 배열을 참조할 수 없습니다. 그러나 읽기 전용 필드에 저장된 배열의 요소는 변경할 수 있습니다.|  
|CA2106|[CA2106: 보안 어설션](../code-quality/ca2106-secure-asserts.md)|메서드에서 권한을 어설션하는데 호출자에 대해 보안 검사가 수행되지 않습니다. 보안 검사를 수행하지 않고 보안 권한을 어설션하면 코드에 보안상 취약한 부분이 남아 있을 수 있습니다.|  
|CA2107|[CA2107: Deny 및 permitonly 검토](../code-quality/ca2107-review-deny-and-permit-only-usage.md)|PermitOnly 메서드와 CodeAccessPermission.Deny 보안 동작은 [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] 보안에 대해 잘 알고 있는 경우에만 사용해야 합니다. 이러한 보안 동작을 사용하는 코드는 보안 검토를 거쳐야 합니다.|  
|CA2108|[CA2108: 값 형식에서 선언적 보안을 검토 합니다.](../code-quality/ca2108-review-declarative-security-on-value-types.md)|public 또는 protected 값 형식이 데이터 액세스 또는 링크 요청에 의해 보안됩니다.|  
|CA2109|[CA2109: 표시 되는 이벤트 처리기를 검토 합니다.](../code-quality/ca2109-review-visible-event-handlers.md)|public 또는 protected 이벤트 처리 메서드를 발견했습니다. 이벤트 처리 메서드는 반드시 필요한 경우를 제외하고 노출하면 안 됩니다.|  
|CA2111|[CA2111: 포인터를 표시 해야 합니다.](../code-quality/ca2111-pointers-should-not-be-visible.md)|포인터가 전용, 내부 또는 읽기 전용이 아닙니다. 악의적인 코드에서 해당 포인터 값을 변경하여 메모리 내 임의의 위치에 액세스할 수 있게 되거나 애플리케이션 또는 시스템 오류를 발생시킬 수 있습니다.|  
|CA2112|[CA2112: 보안된 형식은 필드를 노출 해야](../code-quality/ca2112-secured-types-should-not-expose-fields.md)|public 또는 protected 형식이 public 필드를 포함하고 링크 요청에 의해 보안됩니다. 코드에 링크 요청으로 보안된 형식의 인스턴스에 대한 액세스 권한이 있으면 코드에서 링크 요청을 만족하지 않아도 해당 형식의 필드에 액세스할 수 있습니다.|  
|CA2114|[CA2114: 메서드 보안은 형식의 상위 집합 이어야 합니다.](../code-quality/ca2114-method-security-should-be-a-superset-of-type.md)|메서드에는 같은 동작에 대해 메서드 수준과 형식 수준의 선언적 보안이 모두 있으면 안 됩니다.|  
|CA2115|[CA2115: GC를 호출 합니다. KeepAlive 네이티브 리소스를 사용 하는 경우](../code-quality/ca2115-call-gc-keepalive-when-using-native-resources.md)|이 규칙에서는 관리되지 않는 리소스가 비관리 코드에서 여전히 사용되고 있는데 종료되려고 할 경우 발생할 수 있는 오류를 감지합니다.|  
|CA2116|[CA2116: APTCA 메서드는 APTCA 메서드만 호출 해야 합니다.](../code-quality/ca2116-aptca-methods-should-only-call-aptca-methods.md)|완전히 신뢰할 수 있는 어셈블리에 APTCA(AllowPartiallyTrustedCallersAttribute) 특성이 있고 이 어셈블리가 부분적으로 신뢰할 수 있는 호출자를 허용하지 않는 다른 어셈블리의 코드를 실행하면 보안상 위험할 수 있습니다.|  
|CA2117|[CA2117: APTCA 형식은 APTCA 기본 형식만 확장 해야](../code-quality/ca2117-aptca-types-should-only-extend-aptca-base-types.md)|완전히 신뢰할 수 있는 어셈블리에 APTCA가 있고 이 어셈블리의 형식이 부분적으로 신뢰할 수 있는 호출자를 허용하지 않는 형식에서 상속되면 보안상 위험할 수 있습니다.|  
|CA2118|[CA2118: SuppressUnmanagedCodeSecurityAttribute 사용을 검토 합니다.](../code-quality/ca2118-review-suppressunmanagedcodesecurityattribute-usage.md)|SuppressUnmanagedCodeSecurityAttribute는 COM interop 또는 운영 체제 호출을 사용하는 비관리 코드를 실행하는 멤버에 대해 기본 보안 시스템 동작을 변경합니다. 이 특성은 기본적으로 성능 향상을 위해 사용되지만 성능이 향상되는 대신 중대한 보안 위험이 발생합니다.|  
|CA2119|[CA2119: Private 인터페이스를 만족 하는 메서드를 봉인](../code-quality/ca2119-seal-methods-that-satisfy-private-interfaces.md)|상속할 수 있는 public 형식에서는 internal([!INCLUDE[vbprvb](../includes/vbprvb-md.md)]의 경우 Friend) 인터페이스의 재정의 가능한 메서드 구현을 제공합니다. 이 규칙 위반 문제를 해결하려면 어셈블리 외부에서 메서드가 재정의되지 않도록 합니다.|  
|CA2120|[CA2120: 보안 serialization 생성자](../code-quality/ca2120-secure-serialization-constructors.md)|이 형식에는 System.Runtime.Serialization.SerializationInfo 개체와 System.Runtime.Serialization.StreamingContext 개체(serialization 생성자 서명)를 사용하는 생성자가 있습니다. 이 생성자는 보안 검사를 통해 보안되지 않지만 형식에 있는 하나 이상의 정규 생성자가 보안됩니다.|  
|CA2121|[CA2121: 정적 생성자는 private이어야 합니다.](../code-quality/ca2121-static-constructors-should-be-private.md)|시스템에서는 형식의 첫 번째 인스턴스가 만들어지거나 static 멤버가 참조되기 전에 static 생성자를 호출합니다. static 생성자가 private이 아니면 시스템 이외의 코드에서 이를 호출할 수 있습니다. 이렇게 되면 생성자에서 수행하는 작업에 따라 예기치 않은 동작이 발생할 수 있습니다.|  
|CA2122|[CA2122: 링크 요청이 있는 메서드를 간접적으로 노출 하지 마십시오](../code-quality/ca2122-do-not-indirectly-expose-methods-with-link-demands.md)|public 또는 protected 멤버에 링크 요청이 있으며 해당 멤버가 보안 검사를 수행하지 않는 멤버에 의해 호출됩니다. 링크 요청은 직접 실행 호출자의 권한만 검사합니다.|  
|CA2123|[CA2123: 재정의 링크 요청 기본 동일 해야 합니다.](../code-quality/ca2123-override-link-demands-should-be-identical-to-base.md)|이 규칙에서는 메서드를 다른 형식의 인터페이스이거나 가상 메서드인 기본 메서드에 일치시킨 다음 각각에 대해 링크 요청을 비교합니다. 이 규칙이 위반되면 악의적인 호출자가 보안되지 않은 메서드를 호출함으로써 링크 요청을 우회할 수 있습니다.|  
|CA2124|[CA2124: 취약 한 finally 절 외부 try에](../code-quality/ca2124-wrap-vulnerable-finally-clauses-in-outer-try.md)|public 또는 protected 메서드에 try/finally 블록이 들어 있습니다. finally 블록이 보안 상태를 다시 설정하는 것으로 나타나며 finally 블록에 포함되어 있지 않습니다.|  
|CA2126|[CA2126: 형식 링크 요청은 상속 요청이 필요합니다.](../code-quality/ca2126-type-link-demands-require-inheritance-demands.md)|public unsealed 형식이 링크 요청으로 보호되며 재정의 가능한 메서드를 포함합니다. 형식이나 메서드는 모두 상속 요청으로 보호됩니다.|  
|CA2127|[CA2136: 멤버 충돌 하는 투명도 주석을 가져서는 안](../code-quality/ca2136-members-should-not-have-conflicting-transparency-annotations.md)|100% 투명 어셈블리에서는 중요 코드가 나타날 수 없습니다. 이 규칙은 형식, 필드 및 메서드 수준에서 100% 투명 어셈블리의 SecurityCritical 주석을 분석합니다.|  
|CA2128|[CA2147: 투명 한 메서드는 보안을 사용할 수 없습니다 어설션](../code-quality/ca2147-transparent-methods-may-not-use-security-asserts.md)|이 규칙은 100% 투명 어셈블리나 투명/중요 혼합 어셈블리의 모든 메서드와 형식을 분석하고 선언적이거나 명령적인 어설션 사용에 플래그를 지정합니다.|  
|CA2129|[CA2140: 투명 코드는 보안에 중요 한 항목을 참조 하지 않아야](../code-quality/ca2140-transparent-code-must-not-reference-security-critical-items.md)|SecurityTransparentAttribute로 표시된 메서드가 SecurityCritical로 표시된 public이 아닌 멤버를 호출합니다. 이 규칙은 투명/중요 혼합 어셈블리의 모든 메서드와 형식을 분석하고 투명 코드에서 SecurityTreatAsSafe로 표시되지 않은 public이 아닌 중요 코드를 대상으로 하는 모든 호출을 플래그합니다.|  
|CA2130|[CA2130: 보안 위험 상수는 투명 해야 합니다.](../code-quality/ca2130-security-critical-constants-should-be-transparent.md)|런타임에 조회가 필요하지 않도록 컴파일러에서 상수 값을 인라인하기 때문에 상수 값에 투명성이 적용되지 않습니다. 상수 필드는 보안 투명해야 하므로 코드 검토자는 투명 코드가 상수에 액세스할 수 없다고 가정하지 않습니다.|  
|CA2131|[CA2131: 보안에 중요 한 형식은 형식 등가에 참여할 수 없습니다](../code-quality/ca2131-security-critical-types-may-not-participate-in-type-equivalence.md)|형식이 형식 동등에 참여하는데, 해당 형식 자체 또는 해당 형식의 멤버나 필드가 SecurityCriticalAttribute 특성을 사용하여 표시되어 있습니다. 이 규칙은 중요한 형식 또는 중요한 메서드나 필드를 포함하는 형식이 형식 동등에 참여하는 경우에 적용됩니다. CLR에서 이러한 형식이 검색되면 런타임에 해당 형식이 로드되지 않고 TypeLoadException이 throw됩니다. 일반적으로 이 규칙은 사용자가 tlbimp와 컴파일러를 이용하여 형식 동등을 수행하는 대신 수동으로 형식 동등을 구현하는 경우에만 적용됩니다.|  
|CA2132|[CA2132: 기본 생성자는 최소한 기본 형식 기본 생성자 만큼 중요 해야 합니다.](../code-quality/ca2132-default-constructors-must-be-at-least-as-critical-as-base-type-default-constructors.md)|SecurityCriticalAttribute가 있는 형식 및 멤버는 Silverlight 애플리케이션 코드에서 사용할 수 없습니다. 보안에 중요한 형식 및 멤버는 [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] for Silverlight 클래스 라이브러리의 신뢰할 수 있는 코드에서만 사용할 수 있습니다. 파생 클래스의 public 또는 protected 구성 요소는 투명성이 기본 클래스보다 높거나 같아야 하기 때문에 애플리케이션의 클래스는 SecurityCritical로 표시된 클래스에서 파생될 수 없습니다.|  
|CA2133|[CA2133: 대리자는 투명도 일관 된 메서드에 바인딩해야 합니다.](../code-quality/ca2133-delegates-must-bind-to-methods-with-consistent-transparency.md)|이 경고는 SecurityCriticalAttribute를 사용하여 표시된 대리자를 SecuritySafeCriticalAttribute를 사용하여 표시되거나 투명한 메서드에 바인딩하는 메서드에서 발생합니다. 또한 투명하거나 안전에 중요한 대리자를 중요한 메서드에 바인딩하는 메서드에서도 이 경고가 발생합니다.|  
|CA2134|[CA2134: 메서드는 기본 메서드를 재정의할 때 일관 된 투명도 유지 해야 합니다.](../code-quality/ca2134-methods-must-keep-consistent-transparency-when-overriding-base-methods.md)|이 규칙은 SecurityCriticalAttribute를 사용하여 표시된 메서드가 SecuritySafeCriticalAttribute를 사용하여 표시되거나 투명한 메서드를 재정의할 때 적용됩니다. 또한 SecuritySafeCriticalAttribute를 사용하여 표시되거나 투명한 메서드가 SecurityCriticalAttribute를 사용하여 표시된 메서드를 재정의할 때도 이 규칙이 적용됩니다. 이 규칙은 가상 메서드를 재정의하거나 인터페이스를 구현할 때 적용됩니다.|  
|CA2135|[CA2135: 수준 2 어셈블리는 LinkDemands를 포함 하지](../code-quality/ca2135-level-2-assemblies-should-not-contain-linkdemands.md)|LinkDemands는 수준 2 보안 규칙 집합에서 사용되지 않습니다. JIT 컴파일 시 보안을 적용하는 데 LinkDemands를 사용하는 대신, 해당 메서드, 형식 및 필드를 SecurityCriticalAttribute 특성으로 표시하십시오.|  
|CA2136|[CA2136: 멤버 충돌 하는 투명도 주석을 가져서는 안](../code-quality/ca2136-members-should-not-have-conflicting-transparency-annotations.md)|투명성 특성은 큰 범위의 코드 요소에서 작은 범위의 요소에 적용됩니다. 범위가 큰 코드 요소의 투명성 특성은 첫 번째 요소에 포함된 코드 요소의 투명성 특성보다 우선합니다. 예를 들어 SecurityCriticalAttribute를 사용하여 표시된 클래스에는 SecuritySafeCriticalAttribute 특성을 사용하여 표시된 메서드가 포함될 수 없습니다.|  
|CA2137|[CA2137: 투명 한 메서드는 안정형 IL만 있어야 합니다.](../code-quality/ca2137-transparent-methods-must-contain-only-verifiable-il.md)|메서드가 확인할 수 없는 코드를 포함하거나 형식을 참조로 반환합니다. 이 규칙은 보안 투명 코드에서 확인할 수 없는 MSIL(Microsoft Intermediate Language)을 실행하려고 할 때 적용됩니다. 그러나 이 규칙은 완전한 IL 검증 도구를 포함하지 않으며 대신 추론을 사용하여 MSIL 확인 시 대부분의 위반을 catch합니다.|  
|CA2138|[CA2138: 투명 한 메서드는 SuppressUnmanagedCodeSecurity 특성을 사용 하 여 메서드를 호출 해서는](../code-quality/ca2138-transparent-methods-must-not-call-methods-with-the-suppressunmanagedcodesecurity-attribute.md)|보안 투명 메서드가 SuppressUnmanagedCodeSecurityAttribute 특성을 사용하여 표시된 메서드를 호출합니다.|  
|CA2139|[CA2139: 투명 한 메서드는 HandleProcessCorruptingExceptions 특성을 사용할 수 없습니다.](../code-quality/ca2139-transparent-methods-may-not-use-the-handleprocesscorruptingexceptions-attribute.md)|이 규칙은 HandleProcessCorruptedStateExceptionsAttribute 특성을 사용하여 프로세스 손상 예외를 처리하려고 시도하는 모든 투명한 메서드에 적용됩니다. 프로세스 손상 예외는 AccessViolationException과 같은 예외의 CLR 버전 4.0 예외 분류입니다. HandleProcessCorruptedStateExceptionsAttribute 특성은 보안에 중요한 메서드에서만 사용할 수 있으며 투명 메서드에 적용되는 경우 무시됩니다.|  
|CA2140|[CA2140: 투명 코드는 보안에 중요 한 항목을 참조 하지 않아야](../code-quality/ca2140-transparent-code-must-not-reference-security-critical-items.md)|SecurityCriticalAttribute 특성을 사용하여 표시된 코드 요소는 보안에 중요합니다. 투명 메서드는 보안에 중요한 요소를 사용할 수 없습니다. 투명 형식이 보안에 중요한 형식을 사용하려고 시도하는 경우 TypeAccessException, MethodAccessException 또는 FieldAccessException이 발생합니다.|  
|CA2141|[CA2141: 투명한 메서드는 LinkDemands를 충족해서는 안 됩니다.](../code-quality/ca2141-transparent-methods-must-not-satisfy-linkdemands.md)|보안 투명 메서드가 APTCA를 사용하여 표시되지 않은 어셈블리의 메서드를 호출하거나, 보안 투명 메서드가 형식 또는 메서드에 대한 LinkDemand를 충족합니다.|  
|CA2142|[CA2142: 투명 코드는 LinkDemands를 사용 하 여 보호 해서는 안](../code-quality/ca2142-transparent-code-should-not-be-protected-with-linkdemands.md)|이 규칙은 액세스하는 데 LinkDemands가 필요한 투명한 메서드에 적용됩니다. 보안 투명 코드는 작업 보안을 확인할 책임이 없으므로 권한을 요구해서는 안 됩니다.|  
|CA2143|[CA2143: 투명 한 메서드는 보안 요청을 사용 하지 않아야](../code-quality/ca2143-transparent-methods-should-not-use-security-demands.md)|보안 투명 코드는 작업 보안을 확인할 책임이 없으므로 권한을 요구해서는 안 됩니다. 보안 투명 코드는 보안에 중요한 결정을 내리는 데 전체 요청을 사용해야 하며 안전에 중요한 코드는 전체 요청을 위해 투명 코드를 사용해서는 안 됩니다.|  
|CA2144|[CA2144: 투명 코드는 바이트 배열에서 어셈블리를 로드 하지](../code-quality/ca2144-transparent-code-should-not-load-assemblies-from-byte-arrays.md)|투명 코드는 보안에 중요한 동작을 수행할 수 없기 때문에 투명 코드의 보안 검토는 중요 코드에 대한 보안 검토만큼 완벽하지 않습니다. 바이트 배열에서 로드된 어셈블리는 투명 코드에서 발견되지 않을 수 있으며 해당 바이트 배열은 감사할 필요가 있는 중요하거나 특히 안전에 중요한 코드를 포함할 수 있습니다.|  
|CA2145|[CA2145: 투명 한 메서드는 SuppressUnmanagedCodeSecurityAttribute로 데코레이팅 해야](../code-quality/ca2145-transparent-methods-should-not-be-decorated-with-the-suppressunmanagedcodesecurityattribute.md)|SuppressUnmanagedCodeSecurityAttribute 특성으로 데코레이팅된 메서드에 이를 호출하는 메서드에 대한 암시적 LinkDemand가 배치되어 있습니다. 이 LinkDemand는 호출 코드가 보안을 중요시 하도록 요구합니다. SuppressUnmanagedCodeSecurity를 사용하는 메서드를 SecurityCriticalAttribute 특성으로 표시하면 이 요구 사항이 메서드 호출자에 더욱 명확하게 전달됩니다.|  
|CA2146|[CA2146: 형식은 최소한 기본 형식 및 인터페이스 만큼 중요 해야 합니다.](../code-quality/ca2146-types-must-be-at-least-as-critical-as-their-base-types-and-interfaces.md)|이 규칙은 파생 형식에 기본 형식 또는 구현된 인터페이스만큼 중요하지 않은 보안 투명성 특성이 있을 때 적용됩니다. 중요한 기본 형식에서 파생되거나 중요한 인터페이스를 구현할 수 있는 것은 중요한 형식뿐이고, 안전에 중요한 기본 형식에서 파생되거나 안전에 중요한 인터페이스를 구현할 수 있는 것은 중요하거나 안전에 중요한 형식뿐입니다.|  
|CA2147|[CA2147: 투명 한 메서드는 보안을 사용할 수 없습니다 어설션](../code-quality/ca2147-transparent-methods-may-not-use-security-asserts.md)|SecurityTransparentAttribute로 표시된 코드에는 어설션하는 데 필요한 권한이 부여되지 않습니다.|  
|CA2149|[CA2149: 투명 한 메서드는 네이티브 코드를 호출 하지](../code-quality/ca2149-transparent-methods-must-not-call-into-native-code.md)|이 규칙은 P/Invoke 등을 통해 네이티브 코드를 직접 호출하는 모든 투명 메서드에 적용됩니다. 이 규칙이 위반되면 수준 2 투명성 모델에서 MethodAccessException이 발생하고 수준 1 투명성 모델에서 UnmanagedCode에 대한 완전 요청이 발생합니다.|  
|CA2151|[CA2151: 중요 한 형식을 사용 하 여 필드에는 보안에 중요 한를 사용 해야 합니다.](../code-quality/ca2151-fields-with-critical-types-should-be-security-critical.md)|보안 중요 형식을 사용하려면 이 형식을 참조하는 코드가 보안 중요 또는 보안 안전 중요여야 합니다. 참조가 간접적인 경우에도 마찬가지입니다. 따라서 투명 코드는 필드에 액세스할 수 없으므로 보안 투명 또는 보안 안전 중요 필드가 있을 경우 잘못 해석됩니다.|  
|CA2200|[CA2200: 스택 정보를 유지 하도록 다시 throw](../code-quality/ca2200-rethrow-to-preserve-stack-details.md)|예외가 다시 throw되며 예외가 throw 문에 명시적으로 지정되어 있습니다. throw 문에 예외를 지정하여 예외가 다시 throw되면 예외를 throw한 원래 메서드와 현재 메서드 간의 메서드 호출 목록이 손실됩니다.|  
|CA2201|[CA2201: 예약 된 예외 형식을 발생 하지 않습니다](../code-quality/ca2201-do-not-raise-reserved-exception-types.md)|따라서 원래 오류를 감지하고 디버깅하기 어렵게 됩니다.|  
|CA2202|[CA2202: 개체가 여러 번 삭제 하지 마십시오](../code-quality/ca2202-do-not-dispose-objects-multiple-times.md)|같은 개체에 대해 System.IDisposable.Dispose 또는 Dispose와 동일한 기능의 메서드(예를 들어, 일부 형식의 Close() 메서드)가 여러 번 호출될 수 있는 코드 경로가 메서드 구현에 포함되어 있습니다.|  
|CA2204|[CA2204: 리터럴 철자가 맞아야 합니다.](../code-quality/ca2204-literals-should-be-spelled-correctly.md)|메서드 본문의 리터럴 문자열에 Microsoft 맞춤법 검사 라이브러리에서 인식하지 못하는 단어가 하나 이상 있습니다.|  
|CA2205|[CA2205: 관리 되는 Win32 api를 사용 합니다.](../code-quality/ca2205-use-managed-equivalents-of-win32-api.md)|운영 체제 호출 메서드가 정의되었고 이와 동일한 기능을 수행하는 메서드가 [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] 클래스 라이브러리에 있습니다.|  
|CA2207|[CA2207: 값 형식 정적 필드를 인라인으로 초기화](../code-quality/ca2207-initialize-value-type-static-fields-inline.md)|값 형식에서 명시적인 정적 생성자를 선언합니다. 이 규칙 위반 문제를 해결하려면 모든 정적 데이터를 선언할 때 초기화하고 정적 생성자를 제거합니다.|  
|CA2208|[CA2208: 인수 예외를 올바르게 인스턴스화](../code-quality/ca2208-instantiate-argument-exceptions-correctly.md)|ArgumentException 또는 ArgumentException에서 파생된 예외 형식의 기본(매개 변수가 없는) 생성자를 호출했거나, ArgumentException 또는 ArgumentException에서 파생된 예외 형식의 매개 변수가 있는 생성자에 잘못된 문자열 인수가 전달되었습니다.|  
|CA2210|[CA2210: 어셈블리에는 올바른 강력한 이름을 사용 해야 합니다.](../code-quality/ca2210-assemblies-should-have-valid-strong-names.md)|강력한 이름은 클라이언트에서 무단으로 변경된 어셈블리를 모르는 사이에 로드하지 못하도록 보호합니다. 강력한 이름이 없는 어셈블리는 극히 제한된 시나리오 이외에는 배포하면 안 됩니다. 제대로 서명되지 않은 어셈블리를 공유하거나 배포하면 어셈블리가 무단으로 변경되거나, 공용 언어 런타임에서 어셈블리를 로드할 수 없거나, 사용자가 자신의 컴퓨터에서 확인을 사용하지 못하게 될 수 있습니다.|  
|CA2211|[CA2211: 비상수 필드를 표시 해야 합니다.](../code-quality/ca2211-non-constant-fields-should-not-be-visible.md)|상수도 아니고 읽기 전용도 아닌 정적 필드는 스레드로부터 안전하지 않습니다. 이러한 필드에 대한 액세스는 신중하게 제어해야 하며 클래스 개체에 대한 액세스를 동기화하는 고급 프로그래밍 기술을 필요로 합니다.|  
|CA2212|[CA2212: WebMethod 사용 하 여 서비스 구성 요소를 표시 하지 않음](../code-quality/ca2212-do-not-mark-serviced-components-with-webmethod.md)|System.EnterpriseServices.ServicedComponent로부터 상속하는 형식의 메서드가 System.Web.Services.WebMethodAttribute로 표시되어 있습니다. WebMethodAttribute 및 ServicedComponent 메서드에는 컨텍스트와 트랜잭션 흐름에 있어 충돌하는 동작 및 요구 사항이 있으므로 메서드의 동작이 일부 시나리오에서 잘못됩니다.|  
|CA2213|[CA2213: 삭제 가능한 필드는 삭제해야 합니다.](../code-quality/ca2213-disposable-fields-should-be-disposed.md)|System.IDisposable을 구현하는 형식이 마찬가지로 IDisposable을 구현하는 형식으로 된 필드를 선언합니다. 필드의 Dispose 메서드가 선언 형식의 Dispose 메서드에 의해 호출되지 않습니다.|  
|CA2214|[CA2214: 생성자의 재정의 가능한 메서드를 호출 하지 마십시오](../code-quality/ca2214-do-not-call-overridable-methods-in-constructors.md)|생성자가 가상 메서드를 호출할 때 이 메서드를 호출하는 인스턴스의 생성자가 실행되지 않았을 가능성이 있습니다.|  
|CA2215|[CA2215: Dispose 메서드는 기본 클래스 dispose를 호출 해야 합니다.](../code-quality/ca2215-dispose-methods-should-call-base-class-dispose.md)|삭제 가능한 형식으로부터 상속하는 형식은 자신의 Dispose 메서드에서 기본 형식의 Dispose 메서드를 호출해야 합니다.|  
|CA2216|[CA2216: 삭제 가능한 형식은 종료자를 선언 해야 합니다.](../code-quality/ca2216-disposable-types-should-declare-finalizer.md)|System.IDisposable을 구현하고, 관리되지 않는 리소스의 사용을 암시하는 필드를 포함하는 형식이 Object.Finalize에 설명된 대로 종료자를 구현하지 않습니다.|  
|CA2217|[CA2217: 열거형을 FlagsAttribute로 표시 하지 마십시오.](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)|외부에서 볼 수 있는 열거형이 FlagsAttribute로 표시되어 있고, 2의 거듭제곱 또는 열거형에 정의된 다른 값의 조합이 아닌 값이 하나 이상 들어 있습니다.|  
|CA2218|[CA2218: Equals GetHashCode를 재정의 합니다.](../code-quality/ca2218-override-gethashcode-on-overriding-equals.md)|GetHashCode는 현재 인스턴스를 기반으로 해싱 알고리즘 및 해시 테이블과 같은 데이터 구조체에 적합한 값을 반환합니다. 형식이 같은 동일한 두 개체는 동일한 해시 코드를 반환해야 합니다.|  
|CA2219|[CA2219: Exception 절에서 예외를 발생 하지 않습니다](../code-quality/ca2219-do-not-raise-exceptions-in-exception-clauses.md)|finally 또는 fault 절에서 예외가 발생하는 경우 새 예외가 활성 예외를 숨깁니다. filter 절에서 예외가 발생하는 경우 런타임이 자동으로 예외를 catch합니다. 따라서 원래 오류를 감지하고 디버깅하기 어렵게 됩니다.|  
|CA2220|[CA2220: 종료자는 기본 클래스 종료자를 호출 해야 합니다.](../code-quality/ca2220-finalizers-should-call-base-class-finalizer.md)|종료는 상속 계층을 통해 전파되어야 합니다. 이를 위해 형식은 자체 Finalize 메서드에서 기본 클래스의 Finalize 메서드를 호출해야 합니다.|  
|CA2221|[CA2221: 종료자는 protected 여야](../code-quality/ca2221-finalizers-should-be-protected.md)|종료자에서는 패밀리 액세스 한정자를 사용해야 합니다.|  
|CA2222|[CA2222: 노출 수준을 낮추지 마십시오 상속 된 멤버 표시 유형](../code-quality/ca2222-do-not-decrease-inherited-member-visibility.md)|상속된 멤버에 대한 액세스 한정자는 변경하면 안 됩니다. 상속된 멤버를 private으로 변경하더라도 호출자가 메서드의 기본 클래스 구현에 액세스하는 것을 막을 수 없습니다.|  
|CA2223|[CA2223: 멤버 반환 형식 이외의 달라 야 합니다.](../code-quality/ca2223-members-should-differ-by-more-than-return-type.md)|공용 언어 런타임에서는 반환 값만 다르고 다른 면에서는 동일한 멤버를 구분할 수 있지만 이 기능은 공용 언어 사양에 해당되지 않으며 .NET 프로그래밍 언어의 공통 기능이 아닙니다.|  
|CA2224|[CA2224: 같음 연산자를 오버 로드할 때 equals 재정의](../code-quality/ca2224-override-equals-on-overloading-operator-equals.md)|public 형식이 같음 연산자를 구현하지만 Object.Equals를 재정의하지 않습니다.|  
|CA2225|[CA2225: 연산자 오버 로드는 명명 된 대체](../code-quality/ca2225-operator-overloads-have-named-alternates.md)|연산자 오버로드가 감지되었으며 예상되는 이름의 대체 메서드를 찾을 수 없습니다. 명명된 대체 멤버는 해당 연산자와 동일한 기능에 액세스할 수 있도록 해주며, 오버로드된 연산자가 지원되지 않는 언어로 프로그래밍하는 개발자에게 제공됩니다.|  
|CA2226|[CA2226: 연산자에는 대칭 오버 로드가 있어야 합니다.](../code-quality/ca2226-operators-should-have-symmetrical-overloads.md)|형식이 같음 연산자 또는 같지 않음 연산자를 구현하면서 그 반대 연산자를 구현하지 않습니다.|  
|CA2227|[CA2227: 컬렉션 속성은 읽기 전용 이어야](../code-quality/ca2227-collection-properties-should-be-read-only.md)|쓰기 가능한 컬렉션 속성을 통해 사용자는 컬렉션을 다른 컬렉션으로 바꿀 수 있습니다. 읽기 전용 속성은 컬렉션을 바꾸지 못하도록 하지만 개별 멤버를 설정하는 것은 여전히 가능합니다.|  
|CA2228|[CA2228: 릴리스되지 않은 리소스 형식을 제공 하지 마십시오.](../code-quality/ca2228-do-not-ship-unreleased-resource-formats.md)|[!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] 시험판 버전을 사용하여 빌드된 리소스 파일은 지원되는 [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] 버전에서 사용하지 못할 수 있습니다.|  
|CA2229|[CA2229: serialization 생성자를 구현하십시오.](../code-quality/ca2229-implement-serialization-constructors.md)|이 규칙 위반 문제를 해결하려면 serialization 생성자를 구현합니다. 봉인 클래스의 경우에는 생성자를 private으로 만들고, 그 밖의 경우에는 protected로 만듭니다.|  
|CA2230|[CA2230: 가변 인수로 params를 사용](../code-quality/ca2230-use-params-for-variable-arguments.md)|public 또는 protected 형식에 params 키워드 대신 VarArgs 호출 규칙을 사용하는 public 또는 protected 메서드가 들어 있습니다.|  
|CA2231|[CA2231: ValueType.Equals를 재정의할 때 같음 연산자를 오버로드하십시오.](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)|값 형식이 Object.Equals를 재정의하지만 같음 연산자를 구현하지 않습니다.|  
|CA2232|[CA2232: Mark Windows Forms 진입점을 STAThread](../code-quality/ca2232-mark-windows-forms-entry-points-with-stathread.md)|STAThreadAttribute는 애플리케이션에 대한 COM 스레딩 모델이 단일 스레드 아파트임을 나타냅니다. 이 특성은 Windows Forms을 사용하는 애플리케이션의 진입점에 있어야 합니다. 이 특성을 생략하면 Windows 구성 요소가 제대로 작동하지 않을 수 있습니다.|  
|CA2233|[CA2233: 연산은 오버플로되지 않아야](../code-quality/ca2233-operations-should-not-overflow.md)|산술 연산을 수행하려면 먼저 피연산자의 유효성을 검사하여 연산의 결과가 관련 데이터 형식의 가능한 값 범위를 벗어나지 않도록 해야 합니다.|  
|CA2234|[CA2234: 문자열 대신 System.Uri 개체를 전달 합니다.](../code-quality/ca2234-pass-system-uri-objects-instead-of-strings.md)|이름에 "uri", "URI", "urn", "URN", "url" 또는 "URL"이 포함된 문자열 매개 변수가 있는 메서드가 호출되었습니다. 메서드의 선언 형식에 System.Uri 매개 변수를 가진 해당 메서드 오버로드가 들어 있습니다.|  
|CA2235|[CA2235: 모두 serialize할 수 없는 필드로 표시하십시오.](../code-quality/ca2235-mark-all-non-serializable-fields.md)|serialize할 수 없는 형식의 인스턴스 필드가 serialize할 수 있는 형식에 정의되었습니다.|  
|CA2236|[CA2236: ISerializable 형식에서 기본 클래스 메서드를 호출 합니다.](../code-quality/ca2236-call-base-class-methods-on-iserializable-types.md)|이 규칙 위반 문제를 해결하려면 해당하는 파생된 형식의 메서드나 생성자에서 기본 형식 GetObjectData 메서드나 serialization 생성자를 호출합니다.|  
|CA2237|[CA2237: SerializableAttribute로 ISerializable 형식 표시](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)|공용 언어 런타임에서 serializable로 인식되도록 하려면 형식이 ISerializable 인터페이스 구현을 통해 사용자 지정 serialization 루틴을 사용하는 경우에도 형식을 SerializableAttribute 특성으로 표시해야 합니다.|  
|CA2238|[CA2238: Serialization 메서드를 올바르게 구현 하십시오.](../code-quality/ca2238-implement-serialization-methods-correctly.md)|serialization 이벤트를 처리하는 메서드에 올바른 시그니처, 반환 형식 또는 노출 수준이 없습니다.|  
|CA2239|[CA2239: 선택적 필드에 deserialization 메서드를 제공 합니다.](../code-quality/ca2239-provide-deserialization-methods-for-optional-fields.md)|형식에 System.Runtime.Serialization.OptionalFieldAttribute 특성으로 표시된 필드가 있으며 형식에서 deserialization 이벤트 처리 메서드를 제공하지 않습니다.|  
|CA2240|[CA2240: ISerializable을 올바르게 구현](../code-quality/ca2240-implement-iserializable-correctly.md)|이 규칙 위반 문제를 해결하려면 GetObjectData 메서드를 표시하고 재정의 가능하도록 만든 다음 모든 인스턴스 필드가 serialization 프로세스에 포함되었는지 또는 NonSerializedAttribute 특성으로 명시적으로 표시되었는지 확인합니다.|  
|CA2241|[CA2241: 서식 지정 메서드에 올바른 인수를 제공 합니다.](../code-quality/ca2241-provide-correct-arguments-to-formatting-methods.md)|System.String.Format에 전달된 format 인수에 각 개체 인수에 해당하는 형식 항목이 없거나 각 형식 항목에 해당하는 개체 인수가 없습니다.|  
|CA2242|[CA2242: NaN에 대해 올바르게 테스트](../code-quality/ca2242-test-for-nan-correctly.md)|이 식은 Single.Nan 또는 Double.Nan에 대해 값을 테스트합니다. 값을 테스트하려면 Single.IsNan(Single) 또는 Double.IsNan(Double)을 사용합니다.|  
|CA2243|[CA2243: 특성 문자열 리터럴이 올바르게 구문 분석 되어야 합니다.](../code-quality/ca2243-attribute-string-literals-should-parse-correctly.md)|특성의 문자열 리터럴 매개 변수가 URL, GUID 또는 버전에 대해 구문을 올바르게 분석하지 않습니다.|  
|CA5122|[CA5122: P/Invoke 선언은 안전에 중요한 선언이 아니어야 합니다.](../code-quality/ca5122-p-invoke-declarations-should-not-be-safe-critical.md)|메서드는 보안에 중요한 작업을 수행할 때 SecuritySafeCritical로 표시되지만, 투명 코드에서도 안전하게 사용할 수 있습니다. 투명 코드는 P/Invoke를 통해 절대 네이티브 코드를 직접 호출할 수 없습니다. 따라서 P/Invoke를 SecuritySafeCritical로 표시할 경우 투명 코드가 P/Invoke를 호출할 수 없으며, 보안 분석에서 잘못 해석하는 원인이 됩니다.|
