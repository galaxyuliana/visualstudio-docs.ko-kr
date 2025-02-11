---
title: 로컬 함수를 메서드로 변환
ms.date: 02/19/2019
ms.topic: reference
author: kendrahavens
ms.author: kehavens
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: ccddc3aef24ba14245dc568ca5f369e38ce8eba0
ms.sourcegitcommit: 614d5b99576ea27a41957cd94062dc95cbd29c1c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2019
ms.locfileid: "65531643"
---
# <a name="convert-a-local-function-to-a-method"></a>로컬 함수를 메서드로 변환

이 리팩터링은 다음에 적용됩니다.

- C#
- Visual Basic

**내용:** 로컬 함수를 메서드로 변환합니다.

**시기:** 현재 로컬 컨텍스트 외부에서 정의하려는 로컬 함수가 있습니다.

**이유:** 로컬 함수를 메서드로 변환하여 로컬 컨텍스트 외부에서 호출할 수 있게 하려고 합니다. 로컬 함수가 너무 길어지면 메서드로 변환하는 것이 좋을 수 있습니다. 함수를 별도의 메서드로 정의하면 코드가 더 읽기 쉬워집니다.

## <a name="convert-local-function-to-method-refactoring"></a>로컬 함수를 메서드 리팩터링으로 변환

1. 커서를 로컬 함수에 놓습니다.

    ![로컬 함수를 메서드 코드로 변환 샘플](media/convert-local-function-to-method.png)

2. 줄의 임의 위치에서 **Ctrl**+**.** 를 눌러 **빠른 작업 및 리팩터링** 메뉴를 트리거합니다.

    ![로컬 함수를 메서드 코드 수정 사항으로 변환 샘플](media/convert-local-function-to-method-codefix.png)

2. <Enter> 키를 눌러 리팩터링을 수락합니다.

    ![로컬 함수를 메서드 결과로 변환 샘플](media/convert-local-function-to-method-result.png)

## <a name="see-also"></a>참고 항목

- [리팩터링](../refactoring-in-visual-studio.md)
- [.NET 개발자를 위한 팁](../csharp-developer-productivity.md)
