---
title: Visual C/c + + 사용자 지정 시각화 도우미 호환성
ms.date: 01/28/2019
ms.prod: visual-studio-dev16
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- debugging assertions
- assertions, debugging
- assertions, assertion failures
- Assertion Failed dialog box
ms.assetid: 64af5bed-e38b-420f-b9ce-d64f35100aae
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
monikerRange: '>= vs-2019'
ms.openlocfilehash: a51f2d87b432bf6f4a3925b55622273b56cf5c32
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55920966"
---
# <a name="visual-cc-custom-visualizer-compatibility"></a>Visual C/c + + 사용자 지정 시각화 도우미 호환성

Visual Studio 2019 년부터 Visual c + + 해당 메모리를 많이 사용 구성 요소 호스트에 대 한 외부 64 비트 프로세스를 사용 하는 향상 된 디버거를 포함 합니다. 이 업데이트의 일환으로, Visual C/c + + 식 계산기에 특정 확장명 새 디버거를 사용 하 여 호환 되도록 업데이트 되어야 합니다.

현재 사용 하는 경우 레거시 C/c + + EE 추가 기능 또는 C/c + + 사용자 지정 시각화 도우미를 해제할 수 있습니다이 외부 프로세스의 사용으로 이동 하 여 **도구가** > **옵션**  >   **디버깅**를 선택한 다음 선택을 취소 **(네이티브 전용) 외부 프로세스에서 로드 디버그 기호**합니다. 이 옵션의 선택을 취소 하면 IDE (devenv.exe) 프로세스 내의 메모리 사용량이 크게 증가 발생 합니다. 따라서 대규모 프로젝트를 디버그 하려는 경우이 디버깅 옵션을 사용 하 여 호환 되도록 하려면 확장의 소유자와 협력 하 여 것이 좋습니다.

레거시 C/c + + EE 추가 기능 또는 C/c + + 사용자 지정 시각화 도우미의 소유자 인 경우에 작업자 프로세스에서 확장을 로드 하는 옵트인 하는 방법에 대 한 자세한 정보를 찾을 수 있습니다 합니다 [Concord 확장성 샘플 wiki](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Worker-Process-Remoting)합니다. 찾을 수도 있습니다는 [C/c + + 사용자 지정 시각화 도우미 샘플](https://github.com/Microsoft/ConcordExtensibilitySamples/tree/master/CppCustomVisualizer)합니다.