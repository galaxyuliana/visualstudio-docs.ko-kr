---
title: 대규모 프로젝트 빌드 시 메모리의 효율적인 사용 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- memory use (MSBuild)
- msbuild, efficient memory use building large trees
- caching (MSBuild)
ms.assetid: 853a21ed-69f7-4817-af00-57f73e2c74b5
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5d18f78a0ceec7b79388f53f83909e4dcbcf3b86
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54923535"
---
# <a name="use-memory-efficiently-when-you-build-large-projects"></a>대규모 프로젝트 빌드 시 메모리의 효율적인 사용
대규모 프로젝트는 종종 빌드 시 많은 시스템 메모리를 사용할 수 있는 많은 하위 프로젝트와 다른 종속 파일을 포함합니다. 사용 가능한 시스템 메모리가 감소하는 경우 시스템 성능이 저하될 수 있습니다. 이전 버전의 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 프로젝트는 메모리에 남아 있습니다. 버전 3.5에는 이전 버전의 프로젝트가 제거되었지만 나중에 검색을 위해 캐시에 빌드 결과가 유지되었습니다.  
  
 버전 4.0는 프로젝트에서 `UnloadProjectsOnCompletion` 및 `UseResultsCache`와 같은 속성을 사용할 필요가 없도록 하여 이 메모리 관리를 자동으로 처리합니다.  
  
### <a name="see-also"></a>참고 항목  
 [병렬로 여러 프로젝트 빌드](../msbuild/building-multiple-projects-in-parallel-with-msbuild.md)