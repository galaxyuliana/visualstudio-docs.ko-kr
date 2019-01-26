---
title: DslTextTransform 명령
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language, commands
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.openlocfilehash: 97ddf1fb9dd9e59c2d00f3733069a5cdb14553bf
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55037904"
---
# <a name="the-dsltexttransform-command"></a>DslTextTransform 명령
DslTextTransform.cmd은 TextTransform.exe를 호출 하 고 일반 옵션을 사용 하 여 실행 하는 스크립트. DslTextTransformation.cmd를 사용 하 여의 야간 빌드를 자동화 하 여 [!INCLUDE[dsl](../modeling/includes/dsl_md.md)] 프로젝트입니다. 자세한 내용은 [TextTransform 유틸리티를 사용 하 여 파일 생성](../modeling/generating-files-with-the-texttransform-utility.md)합니다.

 DslTextTransform.cmd은 다음 디렉터리에 있습니다.

 **\<Visual Studio SDK Installation Path>\VisualStudioIntegration\Tools\Bin**

 DslTextTransform.cmd 입력으로는 다음 인수를 지정할 수 있습니다.

- 도메인 모델 프로젝트의 출력 디렉터리입니다.

- 디자이너 정의 프로젝트의 출력 디렉터리입니다.

- 텍스트 템플릿 파일의 위치입니다.

  DslTextTransform.cmd 기본 지시문 프로세서 및 어셈블리를 사용 하 여 지정 된 텍스트 템플릿 파일을 처리 합니다. 사용자 지정 지시문 프로세서를 만드는 경우 TextTransform.exe를 호출 하는 일괄 처리 파일을 만들 수 있습니다. 이 배치 파일에서 어셈블리 및 연관 된 사용자 지정 지시문 프로세서를 지정할 수 있습니다.