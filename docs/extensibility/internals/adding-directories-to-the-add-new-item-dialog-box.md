---
title: 디렉터리에 추가 된 새 항목 추가 대화 상자 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Add New Item dialog box, extending
ms.assetid: 67ae8af6-3752-49e8-8ce3-007aca5f7982
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: bfe4578b4896c137f3bcef8418c5dc0cafd70798
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56604212"
---
# <a name="add-directories-to-the-add-new-item-dialog-box"></a>새 항목 추가 대화 상자에 디렉터리 추가
다음 코드 예제에 대 한 디렉터리의 새 집합을 등록 하는 방법에 설명 합니다 **새 항목 추가** 대화 상자. 에 대 한 디렉터리를 **새 항목 추가** 대화 상자는 각 프로젝트에 대해 다릅니다. 디렉터리 아래에 등록 되며 따라서 합니다 **프로젝트** 하위 키에 있는 **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0Exp\Projects**합니다.

## <a name="registry-script"></a>레지스트리 스크립트

```
NoRemove Projects
{
  NoRemove %GUID_Project%
  {
    NoRemove AddItemTemplates
    {
      NoRemove TemplateDirs
      {
        ForceRemove %CLSID_Package%
        {
      ForceRemove /1 = s '#%Folder_Label_ResID%'
          {
            val TemplatesDir = s '%Template_Path%'
            val SortPriority = d 2000
          }
        }
      }
    }
  }
}
```

 `%Template_Path%` 값 프로젝트 템플릿이 포함 된 디렉터리의 전체 경로 지정 합니다. 이러한 템플릿은 일 수 있습니다 *.vsz* 파일 또는 정형화 된 템플릿 파일을 복제할 수 있습니다.

 `SortPriority` 값 정렬 우선 순위를 지정 합니다.

## <a name="add-items-to-an-existing-project"></a>기존 프로젝트에 항목 추가
 기존 프로젝트에 항목을 추가할 수도 있습니다. 예를 [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] 프로젝트 항목을 추가할 수 있습니다 합니다  *\<루트 > \Program Files\Microsoft Visual Studio\VC #\CSharpProjectItems\LocalProjectItems* 폴더입니다. 이 경우 `%GUID_Project%` C# 프로젝트 ({0} FAE04EC0-301F-11D3-BF4B-00C04F79EFBC})에 대 한 GUID입니다.

 또한 프로젝트 하위 형식 프로그래밍 하 여 기존 프로젝트를 확장할 수 있습니다. 프로젝트 하위 형식을 사용 하 여 새 프로젝트 형식을 작성 하지 않고도 프로젝트를 확장할 수 있습니다. 프로젝트 하위 형식에 대 한 자세한 내용은 참조 하세요. [프로젝트 하위 형식](../../extensibility/internals/project-subtypes.md)합니다.

## <a name="see-also"></a>참고자료
- [프로젝트 및 항목 템플릿을 등록합니다](../../extensibility/internals/registering-project-and-item-templates.md)
- [새 항목 추가 대화 상자에 항목 추가](../../extensibility/internals/adding-items-to-the-add-new-item-dialog-boxes.md)
- [새 프로젝트 대화 상자에 디렉터리 추가](../../extensibility/internals/adding-directories-to-the-new-project-dialog-box.md)