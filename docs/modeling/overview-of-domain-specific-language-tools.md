---
title: 도메인별 언어 도구 개요
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.openlocfilehash: 17a5908ddb6ecdd9f8434de1bd2792c4b86c989d
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54981989"
---
# <a name="overview-of-domain-specific-language-tools"></a>도메인별 언어 도구 개요
Visual Studio에서 호스팅되는 도메인 특정 언어 도구 (DSL 도구)를 사용 하 여 도메인 특정 언어의 디자인과 생성 하는 모든 사용자에 게 필요한 언어를 기반으로 하는 모델을 만들 수 있습니다.

 다음 도구는 DSL 도구에 포함 됩니다.

-   다른 솔루션 템플릿을 사용 하 여 도메인 특정 언어 개발을 시작 하는 데 도움이 되는 프로젝트 마법사.

-   만들고 도메인별 언어 정의 편집 하기 위한 그래픽 디자이너입니다.

-   도메인별 언어 정의 제대로 구성 하 고 문제가 있는 경우 오류 및 경고를 표시 하는 유효성 검사 엔진입니다.

-   입력으로 도메인별 언어 정의 사용 하 고 출력으로 소스 코드를 생성 하는 코드 생성기입니다.

## <a name="the-dsl-tools-solution"></a>DSL 도구 솔루션
 도메인 관련 디자이너 마법사에는 다음 솔루션 템플릿을 제공합니다.

- 작업 흐름

- 클래스 다이어그램

- 최소 언어

- 구성 요소 모델

- 최소한의 WPF

- 최소 Windows.Forms

- DSL 라이브러리

  자세한 내용은 [도메인별 언어 솔루션 템플릿 선택](../modeling/choosing-a-domain-specific-language-solution-template.md)합니다.

  마법사는 다음 프로젝트가 있는 Visual Studio 솔루션을 만듭니다.

- Dsl

   Dsl 프로젝트 도메인 특정 언어 및 해당 편집 및 처리 도구를 정의합니다.

- **DslPackage**

   DslPackage 프로젝트 언어 도구 Visual Studio와 통합 하는 방법을 결정 합니다.

## <a name="the-dsl-tools-graphical-interface"></a>DSL 도구는 그래픽 인터페이스
 도메인 특정 언어에 요소 및 관계를 추가 하려면 DSL 도구 그래픽 인터페이스를 사용할 수 있습니다. 요소를 추가 하면 셰이프에 매핑시키고 하 고 색을 사용자 지정 데코레이터를 추가 하 여 모양을 정의할 수 있습니다. 또한 도구 상자에 요소를 추가할 수 있습니다.

## <a name="validation-in-dsl-tools"></a>DSL 도구에 대 한 유효성 검사
 Dsl에는 한 수준의 도메인 모델 코드 생성에 대 한 기본 요구 사항을 충족 하는지 확인 하도록 유효성 검사를 제공 합니다. 일반적으로 사용자 고유의 도메인 특정 언어를 만들 때 비즈니스 논리 규칙을 표현 하는 유효성을 검사를 직접 추가 합니다. 사용자 지정 유효성 검사에 대 한 자세한 내용은 참조 하세요. [도메인별 언어에서 유효성 검사](../modeling/validation-in-a-domain-specific-language.md)합니다.

 확인 하는 도메인 특정 언어 종종 것을 디자인할 때 하는 것이 좋습니다. 도메인 특정 언어의 유효성 검사 오류가 있으면 소스 코드를 생성할 수 없습니다. 템플릿에서 소스 코드를 생성 하는 과정을 클릭 하 여 수행 됩니다 **모든 템플릿 변환** 솔루션 탐색기의 도구 모음에서입니다. 언어 정의 수정할 때마다 또한 해야 **모든 템플릿 변환**합니다. 자세한 내용은 [방법: 도메인별 언어 솔루션 만들기](../modeling/how-to-create-a-domain-specific-language-solution.md)합니다.

## <a name="customization-of-dsl-tools"></a>DSL 도구에 대 한 사용자 지정
 모델의 동작을 구체화 하 고 언어를 통해 제약 조건을 정의 하려면 추가 코드를 제공할 수 있습니다. 필요한 경우 텍스트 템플릿을 수정 하 여 중요 한 변경 가능 합니다.

## <a name="distributing-your-dsl-solution"></a>DSL 솔루션 배포
 DSL 도구는 Visual Studio에서 호스트 되는 패키지를 생성 합니다. 패키지를 도구 상자, DSL 탐색기 및 도메인 특정 언어를 사용 하 여 모델을 만들 수 있도록 하는 다른 UI 요소를 표시 합니다.

 를 빌드 및 Visual Studio에서 DSL 도구 솔루션을 실행 하는 경우 Visual Studio의 두 번째 인스턴스를 도메인 특정 언어를 언어의 사용자에 게 표시 하는 방법 보여를 줍니다. 모든 항목이 올바르게 작동을 확인 한 후 배포할 수 있습니다는 `.vsix` 파일을 DslPackage 프로젝트의 빌드 폴더에서 찾을 수 있습니다. 이 파일은 DSL을 설치할 다른 컴퓨터에서 Visual Studio 확장으로 사용할 수 있습니다.  자세한 내용은 [도메인별 언어 솔루션 배포](../modeling/deploying-domain-specific-language-solutions.md)합니다.

## <a name="see-also"></a>참고 항목

- [실험적 인스턴스](../extensibility/the-experimental-instance.md)
- [도메인 특정 언어 도구 용어집](https://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)