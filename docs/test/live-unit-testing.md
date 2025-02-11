---
title: Live Unit Testing
ms.date: 03/07/2017
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio ALM
- Live Unit Testing
author: rpetrusha
ms.author: ronpet
ms.workload:
- dotnet
ms.openlocfilehash: bfe1affaad05d2c20a27fb0e315fc1d3b263f22b
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68923746"
---
# <a name="live-unit-testing-with-visual-studio"></a>Visual Studio를 사용한 Live Unit Testing

애플리케이션을 개발할 때 Live Unit Testing은 자동으로 백그라운드에서 영향을 받는 단위 테스트를 실행하고 Visual Studio IDE에서 실시간으로 결과 및 코드 검사 라이브를 표시합니다. 코드를 수정할 때 Live Unit Testing은 변경 내용이 기존 테스트에 영향을 주는 방법 및 추가한 새 코드를 하나 이상의 기존 테스트에서 검사할지 여부에 대한 피드백을 제공합니다. 그러면 버그를 수정하거나 새로운 기능을 추가할 경우에 사용자가 단위 테스트를 작성하도록 알려 줄 수 있습니다.

> [!NOTE]
> Visual Studio의 Enterprise Edition에서 .NET Core 또는 .NET Framework를 대상으로 하는 C# 및 Visual Basic 프로젝트에 Live Unit Testing을 사용할 수 있습니다.

테스트를 위해 Live Unit Testing을 사용하는 경우 Live Unit Testing은 테스트 상태에 대한 데이터를 유지합니다. Live Unit Testing은 영구 데이터를 사용하는 기능을 통해 코드 변경에 대한 응답으로 테스트를 동적으로 실행하는 동안 뛰어난 성능을 제공할 수 있습니다.

## <a name="supported-test-frameworks"></a>지원되는 테스트 프레임워크
Live Unit Testing은 다음 테이블에 나열된 세 가지 인기 있는 단위 테스트 프레임워크를 사용합니다. 해당 어댑터와 프레임워크를 지원하는 최소 버전은 테이블에 나열됩니다. 단위 테스트 프레임워크는 NuGet.org에서 모두 사용할 수 있습니다.

|테스트 프레임워크  |Visual Studio 어댑터 최소 버전  |프레임워크 최소 버전  |
|---------|---------|---------|
|xUnit.net |xunit.runner.visualstudio 버전 2.2.0-beta3-build1187 |xunit 1.9.2 |
|NUnit |NUnit3TestAdapter 버전 3.5.1 |NUnit 버전 3.5.0 |
|MSTest |MSTest.TestAdapter 1.1.4-미리 보기 |MSTest.TestFramework 1.0.5-미리 보기 |

`Microsoft.VisualStudio.QualityTools.UnitTestFramework`를 참조하는 이전 MSTest 기반 테스트 프로젝트가 있고 최신 MSTest NuGet 패키지로 이동하지 않으려면 Visual Studio 2017 버전 15.4 이상으로 업그레이드하세요.

경우에 따라 Live Unit Testing이 작동하기 위해 솔루션의 프로젝트에서 참조하는 NuGet 패키지를 명시적으로 복원해야 합니다. 이렇게 하려면 솔루션의 명시적 빌드를 수행합니다(최상위 Visual Studio 메뉴에서 **빌드** > **솔루션 다시 빌드**를 선택). 또는 Living Unit Testing을 활성화하기 전에 솔루션에서 패키지를 복원합니다(솔루션을 마우스 오른쪽 단추로 클릭하고 **NuGet 패키지 복원**을 선택).

## <a name="configure-live-unit-testing"></a>Live Unit Testing 구성

최상위 Visual Studio 메뉴 모음에서 **도구** > **옵션**을 선택한 다음, **옵션** 대화 상자의 왼쪽 창에서 **Live Unit Testing**을 선택하여 Live Unit Testing을 구성할 수 있습니다.

> [!TIP]
> Live Unit Testing을 사용하면(다음 섹션 [Live Unit Testing 시작 일시 중지 및 중지](#start-pause-and-stop-live-unit-testing) 참조) **테스트** > **Live Unit Testing** > **옵션**을 선택하여 **옵션** 대화 상자를 열 수도 있습니다.

다음 그림에서는 대화 상자에서 사용할 수 있는 Live Unit Testing 구성 옵션을 표시합니다.

  ![이미지](./media/lut-options.png)

구성 가능한 옵션은 다음과 같습니다.

- 솔루션이 빌드되어 디버깅될 때 Live Unit Testing을 일시 중지할지 여부

- 시스템의 배터리 전원이 지정된 임계값 미만인 경우 Live Unit Testing을 일시 중지할지 여부

- 솔루션을 열면 Live Unit Testing을 자동으로 실행할지 여부

- 디버그 기호 및 XML 문서 주석 생성을 사용할지 여부

- 영구 데이터를 저장할 디렉터리입니다.

- 모든 영구 데이터를 삭제하는 기능입니다. Live Unit Testing이 예측할 수 없거나 예기치 않은 방식으로 동작할 때 유용하며 영구 데이터가 손상되었음을 나타냅니다.

- 테스트 사례의 시간이 초과되는 간격은 기본값 30초입니다.

- Live Unit Testing에서 만든 최대 테스트 프로세스의 수입니다.

- Live Unit Testing 프로세스에서 사용할 수 있는 최대 메모리 양입니다.

- Live Unit Testing **출력** 창에 기록된 정보 수준

   옵션에는 로깅되지 않음(**없음**), 오류 메시지만 해당(**오류**), 오류 및 정보 메시지(**정보**, 기본값) 또는 모든 세부 정보(**자세한 정보 표시**)가 포함됩니다.

   `VS_UTE_DIAGNOSTICS`이라는 사용자 수준 환경 변수에 "1" 값을 할당한 다음, Visual Studio를 다시 시작하여 Live Unit Testing **출력** 창에서 자세한 정보 출력을 표시할 수도 있습니다.

   파일의 Live Unit Testing에서 자세한 MSBuild 로그 메시지를 캡처하려면 `LiveUnitTesting_BuildLog` 사용자 수준 환경 변수를 로그를 포함하는 파일 이름으로 설정합니다.

## <a name="start-pause-and-stop-live-unit-testing"></a>Live Unit Testing 시작, 일시 중지 및 중지

최상위 Visual Studio 메뉴에서 **테스트** > **Live Unit Testing** > **시작**을 선택하여 Live Unit Testing을 활성화합니다. Live Unit Testing을 사용하면 **Live Unit Testing** 메뉴에서 사용할 수 있는 옵션이 단일 항목에서 **시작**, **일시 중지**, **중지** 및 **Reset Clean(정리 다시 설정)** 으로 변경됩니다.

> [!NOTE]
> 단위 테스트 프로젝트를 포함하지 않는 솔루션에서 Live Unit Testing을 시작하려면 **일시 중지**, **중지**, **정리 다시 설정** 옵션이 **Live Unit Testing** 메뉴에 나타나지만 Live Unit Testing은 시작되지 않습니다. **출력** 창에는 "이 솔루션에서 참조하는 지원되는 테스트 어댑터가 없습니다..."로 시작되는 메시지가 표시됩니다.

언제든지 Live Unit Testing을 일시적으로 또는 완전히 중지할 수 있습니다. 예를 들어, 리팩터링하는 중에 이렇게 하려면 테스트가 한 동안 중단된다는 점을 고려하세요. 세 가지 메뉴 옵션은 다음과 같습니다.

- **일시 중지**는 Live Unit Testing을 일시적으로 중단합니다.

    Live Unit Testing이 일시 중지되면 검사 시각화는 편집기에 표시되지 않지만 수집된 모든 데이터는 유지되었습니다. Live Unit Testing을 다시 시작하려면 Live Unit Testing 메뉴에서 **계속**을 선택합니다. Live Unit Testing은 일시 중지되는 동안 수행한 모든 편집 내용을 적용하는 데 필요한 작업을 수행하고 문자 모양을 적절하게 업데이트합니다.

- **중지**는 Live Unit Testing을 완전히 중지합니다. Live Unit Testing은 수집된 모든 데이터를 삭제합니다.

- **Reset Clean(정리 다시 설정)** 을 선택하면 Live Unit Testing을 중지하고 영구 데이터를 삭제하며 Live Unit Testing을 다시 시작합니다.

- **옵션**을 선택하면 [Live Unit Testing 구성](#configure-live-unit-testing) 섹션에서 설명한 **옵션** 대화 상자가 열립니다.

## <a name="view-coverage-visualization-in-the-editor-as-you-type"></a>입력할 때 편집기에서 검사 시각화 보기

Live Unit Testing은 일단 활성화되면 Visual Studio 편집기에서 코드 줄 각각을 업데이트하여 작성한 코드에 단위 테스트가 적용되는지 및 적용된 테스트에 통과하는지 여부를 표시합니다.  다음 그림에서는 테스트를 통과하거나 실패한 코드 줄뿐만 아니라 테스트가 적용되지 않은 코드 줄을 보여 줍니다. 녹색 “✓” 표시가 있는 줄은 테스트를 통과한 경우에만 적용됩니다. 빨간색 “x”로 표시된 줄은 하나 이상의 테스트에 실패한 경우 적용됩니다. 파란색 “➖”로 표시된 줄은 테스트되지 않은 경우에 적용됩니다.

  ![이미지](./media/lut-codewindow.png)

코드 편집기에서 코드를 수정하면 즉시 Live Unit Testing 검사 시각화가 업데이트됩니다. 편집 내용을 처리하는 동안 다음 그림과 같이 통과, 실패 아래에 적용된 기호가 아닌 라운드 타이머를 추가하여 데이터가 최신 상태가 아님을 나타내도록 시각화가 변경됩니다.

  ![이미지](./media/lut-codeupdating.png)

## <a name="get-information-on-successful-or-failed-tests"></a>성공하거나 실패한 테스트에 대한 정보 가져오기

코드 창에서 성공하거나 실패한 기호를 마우스로 가리키면 해당 줄에 도달한 테스트 수를 확인할 수 있습니다. 기호를 클릭하면 다음 그림에서처럼 개별 테스트의 상태를 볼 수 있습니다.

  ![이미지](./media/lut-failedinfo.png)

이름 및 테스트 결과를 제공하는 것 외에도, 도구 설명을 통해 일련의 테스트를 다시 실행하고 디버거를 사용하여 일련의 테스트를 실행할 수 있습니다. 도구 설명에서 테스트를 하나 이상 선택하면 해당 테스트만 실행하거나 디버깅할 수도 있습니다. 따라서 코드 창을 벗어나지 않고도 테스트를 디버깅할 수 있습니다. 디버깅할 때는 이미 설정된 중단점을 관찰하는 것 외에도, 디버거가 예기치 않은 결과를 반환하는 [`Assert`](/dotnet/api/microsoft.visualstudio.testtools.unittesting.assert) 메서드를 실행할 때 프로그램 실행을 일시 중지합니다.

도구 설명에서 실패한 테스트를 마우스로 가리키면 다음 이미지에 표시된 대로 확장되어 오류에 대한 추가 정보를 제공합니다. 도구 설명에서 실패한 테스트를 두 번 클릭하면 해당 테스트로 이동할 수 있습니다.

  ![이미지](./media/lut-failedmsg.png)

실패한 테스트로 이동하면 Live Unit Testing은 메서드 시그니처에 통과한 테스트(녹색 “✓”와 함께 반쯤 채워진 비커로 표시), 실패한 테스트(빨간색 “🞩”와 함께 반쯤 채워진 비커) 또는 Live Unit Testing에 포함되지 않은 테스트(파란색 “➖”와 함께 반쯤 채워진 비커)를 시각적으로 표시합니다. 테스트 이외의 메서드는 기호로 데코레이팅되지 않습니다. 다음 그림에서는 네 가지 형식의 모든 메서드를 보여 줍니다.

  ![이미지](media/lut-testsource.png)

## <a name="diagnose-and-correct-test-failures"></a>테스트 실패 진단 및 해결

실패한 테스트에서 제품 코드에 쉽게 디버깅하고 편집을 수행하며 애플리케이션을 계속 개발할 수 있습니다. Live Unit Testing이 백그라운드에서 실행되므로 디버그, 편집 및 진행 주기 동안 Live Unit Testing을 중지했다가 다시 시작할 필요는 없습니다.

예를 들어 이전 그림에 표시된 테스트 오류로 인해 테스트 메서드에서 알파벳이 아닌 문자가 <xref:System.Char.IsLower%2A?displayProperty=fullName> 메서드에 전달될 때 `true`을 반환한다는 잘못된 가정을 발생시켰습니다. 테스트 메서드를 수정하면 모든 테스트를 통과합니다. 이러는 동안 Live Unit Testing을 일시 중지하거나 중지할 필요는 없습니다.

## <a name="live-unit-testing-and-test-explorer"></a>Live Unit Testing 및 Test Explorer

일반적으로 **Test Explorer**는 테스트 결과를 실행, 디버그 및 분석할 수 있게 해 주는 인터페이스를 제공합니다. Live Unit Testing은 **Test Explorer**와 통합됩니다. Live Unit Testing이 사용되지 않거나 중지되면 **Test Explorer**는 마지막으로 테스트를 실행한 단위 테스트의 상태를 표시합니다. 소스 코드를 변경하려면 테스트를 다시 실행해야 합니다. 반면에 Live Unit Testing을 사용하는 경우 **Test Explorer**에서 단위 테스트의 상태가 즉시 업데이트됩니다. 더 이상 단위 테스트를 명시적으로 실행할 필요가 없습니다.

> [!NOTE]
> 최상위 Visual Studio 메뉴에서 **테스트** > **Windows** > **테스트 탐색기**를 선택하여 **테스트 탐색기**를 열 수 있습니다.

**Test Explorer** 창에서 일부 테스트가 흐리게 표시된 것을 알 수 있습니다. 예를 들어 이전에 저장한 프로젝트를 연 후 Live Unit Testing을 활성화하면 다음 그림과 같이 **Test Explorer** 창에는 실패한 테스트를 제외한 모든 항목이 흐리게 표시됩니다. 이 경우 Live Unit Testing의 영구 데이터는 테스트가 마지막으로 성공적으로 실행된 후 변경되지 않았으므로 Live Unit Testing은 실패한 테스트를 다시 실행하지만 성공한 테스트는 다시 실행하지 않습니다.

  ![이미지](media/lut-test-explorer.png)

**Test Explorer** 메뉴에서 **모두 실행** 또는 **실행** 옵션을 선택하거나 **Test Explorer** 메뉴에서 테스트를 하나 이상 선택하거나 마우스 오른쪽 단추를 클릭하고 팝업 메뉴에서 **선택한 테스트 실행** 또는 **선택한 테스트 디버그**를 선택하여 희미하게 표시된 모든 테스트를 다시 실행할 수 있습니다. 테스트가 실행되면서 맨 위로 버블링됩니다.

Live Unit Testing이 테스트 결과를 자동으로 실행하고 업데이트는 것과 **Test Explorer**에서 테스트를 명시적으로 실행하는 것은 다릅니다. 이러한 차이점에는 다음이 포함됩니다.

- Test Explorer 창에서 테스트를 실행 또는 디버깅하면 일반 이진 파일을 실행합니다. 반면 Live Unit Testing은 계측된 이진 파일을 실행합니다.
- Live Unit Testing은 테스트를 실행할 새 애플리케이션 도메인을 만들지 않지만 기본 도메인에서 테스트를 실행합니다. **Test Explorer** 창에서 테스트를 실행하면 새 애플리케이션 도메인을 만들지 않습니다.
- Live Unit Testing은 테스트 어셈블리 각각에서 순차적으로 테스트를 실행합니다. **테스트탐색기** 창에서 여러 테스트를 병렬로 실행하는 옵션을 선택할 수 있습니다.

## <a name="live-unit-testing-and-large-solutions"></a>Live Unit Testing 및 대규모 솔루션

솔루션에 10개 이상의 프로젝트가 있고 Live Unit Testing을 시작할 때 지속형 데이터가 없는 경우 또는 최상위 Visual Studio 메뉴에서 **테스트** > **Live Unit Testing** > **정리 다시 설정** 옵션을 선택하는 경우 Visual Studio에는 다음과 같은 대화 상자가 표시되어 대규모 프로젝트의 많은 테스트를 동적으로 실행 시 상당한 성능 저하가 발생할 수 있음을 경고합니다. **확인**을 선택하면 Live Unit Testing에서 솔루션의 모든 테스트를 실행합니다. **취소**를 선택하면 실행할 테스트를 선택할 수 있습니다. 이 작업을 수행하는 방법은 다음 [테스트 프로젝트 및 테스트 메서드 포함 및 제외](#include-and-exclude-test-projects-and-test-methods) 섹션을 참조하세요.

![대규모 프로젝트에 대한 Live Unit Testing 대화 상자](media/lut-large-project.png)

## <a name="include-and-exclude-test-projects-and-test-methods"></a>테스트 프로젝트 및 테스트 메서드 포함 및 제외

여러 테스트 프로젝트를 포함한 솔루션에서는 Live Unit Testing에 참여하는 프로젝트 및 프로젝트의 개별 메서드를 제어할 수 있습니다. 예를 들어 수백 개의 테스트 프로젝트를 포함한 솔루션을 구현하는 경우 Live Unit Testing에 참여할 테스트 프로젝트의 대상 집합을 선택할 수 있습니다. 프로젝트 또는 솔루션에서 모든 테스트를 제외할 것인지, 대부분의 테스트를 포함시키거나 제외할 것인지 또는 개별적으로 테스트를 제외할 것인지 여부에 따라 다양한 방법으로 수행할 수 있습니다. Live Unit Testing은 포함/제외 상태를 사용자 설정으로 저장하고 솔루션을 닫고 다시 열 경우 불러옵니다.

**프로젝트 또는 솔루션에서 모든 테스트 제외**

단위 테스트에서 개별 프로젝트를 선택하려면 Live Unit Testing을 시작한 후에 다음을 수행합니다.

1. **솔루션 탐색기**에서 솔루션을 마우스 오른쪽 단추로 클릭하고 **라이브 테스트** > **제외**를 선택하여 전체 솔루션을 제외합니다.
1. 테스트에 포함하려는 테스트 프로젝트 각각을 마우스 오른쪽 단추로 클릭하고 **라이브 테스트** > **포함**을 선택합니다.

**코드 편집기 창에서 개별 테스트 제외**

코드 편집기 창을 사용하여 개별 테스트 메서드를 포함하거나 제외시킬 수 있습니다. 코드 편집기 창에서 테스트 메서드의 시그니처를 마우스 오른쪽 단추로 클릭하고 **라이브 테스트** >  **[선택한 메서드] 포함**, **라이브 테스트** >  **[선택한 메서드] 제외** 또는 **라이브 테스트** >  **[선택한 메서드]를 빼고 모두 제외**를 선택합니다. 여기서 "선택한 메서드"는 코드 창에서 선택한 메서드의 이름입니다.

**프로그래밍 방식으로 테스트 제외**

<xref:System.Diagnostics.CodeAnalysis.ExcludeFromCodeCoverageAttribute> 특성을 적용하여 Live Unit Testing에서 해당 검사를 보고하지 않도록 메서드, 클래스 또는 구조를 프로그래밍 방식으로 제외할 수 있습니다.

또한 Live Unit Testing에서 개별 메서드를 제외하려면 다음 특성을 사용할 수 있습니다.

- xUnit: `[Trait("Category", "SkipWhenLiveUnitTesting")]`
- NUnit: `[Category("SkipWhenLiveUnitTesting")]`
- MSTest: `[TestCategory("SkipWhenLiveUnitTesting")]`

## <a name="see-also"></a>참고 항목

- [코드 테스트 도구](https://visualstudio.microsoft.com/vs/testing-tools/)
- [Live Unit Testing 블로그](https://go.microsoft.com/fwlink/?linkid=842514)
- [Live Unit Testing FAQ](live-unit-testing-faq.md)
- [Channel 9 비디오: Visual Studio의 Live Unit Testing](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T105)
