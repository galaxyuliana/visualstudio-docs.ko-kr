---
title: '연습: XSLT IntelliSense 사용 | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: 079d95ac-2eaf-4ae1-9cd3-2c81a961a942
caps.latest.revision: 7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 45cb15a81f7f8f74ab17bf22ce52aca48a90aea9
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68158614"
---
# <a name="walkthrough-using-xslt-intellisense"></a>연습: XSLT IntelliSense 사용
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 연습에서는 XSLT IntelliSense를 사용하여 일부 특성 값을 자동 완성하는 방법을 보여 줍니다.  
  
### <a name="to-use-intellisense-in-the-name-attribute-of-xslwith-param-and-xslcall-template-elements"></a>xsl:with-param 및 xsl:call-template 요소의 이름 특성에 IntelliSense를 사용하려면  
  
1. 새 XSLT 파일을 만들고 다음 코드에 복사합니다.  
  
    ```  
    <xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform" version="1.0">  
    <!-- These 2 elements effectively assign  
         $messages = resources/en.xml/<messages>,  
         then $messages is used in the "localized-message" template.  -->  
    <xsl:param name="lang">en</xsl:param>  
    <xsl:variable name="messages"  
          select="document(concat('resources/', $lang, '.xml'))/messages"/>   
  
    <xsl:template name="msg23" match="msg23">  
    </xsl:template>  
  
    <xsl:template name="localized-message">  
      <xsl:param name="msgcode"/>  
      <!-- Show message string. -->  
      <xsl:message terminate="yes">  
        <xsl:value-of select="$messages/message[@name=$msgcode]"/>  
      </xsl:message>  
    </xsl:template>  
    </xsl:stylesheet>  
    ```  
  
2. 커서를 `<xsl:template name="msg23" match="msg23">` 다음에 놓고 Enter 키를 누릅니다. 그리고 나서 다음 `xsl:call-template` 요소 입력을 시작합니다.  
  
    ```  
    <xsl:call-template name="localized-message">  
    </xsl:call-template>  
    ```  
  
     입력할 때 템플릿 이름의 목록이 `name=""` 요소의 `xsl:call-template` 특성에 나타납니다.  
  
3. 커서를 `<xsl:call-template name="localized-message">` 다음에 놓고 Enter 키를 누릅니다. 그리고 나서 다음 `xsl:with-param` 요소 입력을 시작합니다.  
  
    ```  
    <xsl:with-param name="msgcode">msg23</xsl:with-param>  
    ```  
  
     매개 변수 이름의 목록이 `name=""` 요소의 `xsl:with-param` 특성에 나타납니다.  
  
### <a name="to-use-intellisense-in-the-mode-attribute-of-an-xslapply-templates-element"></a>xsl:apply-templates 요소의 모드 특성에 IntelliSense를 사용하려면  
  
1. 새 XSLT 파일을 만들고 다음 코드에 복사합니다.  
  
    ```  
    <xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform" version="1.0">  
      <xsl:template match="/">  
        <HTML>  
          <BODY>  
            <TABLE>  
              <xsl:apply-templates select="customers/customer">  
                <xsl:sort select="state"/>  
                <xsl:sort select="name"/>  
              </xsl:apply-templates>  
            </TABLE>  
          </BODY>  
        </HTML>  
      </xsl:template>  
      <xsl:template match="customer">  
        <TR>  
          <xsl:apply-templates select="name" />  
          <xsl:apply-templates select="address" />  
          <xsl:apply-templates select="phone" />  
        </TR>  
      </xsl:template>  
      <xsl:template match="name">  
        <TD STYLE="font-size:14pt font-family:serif">  
          <xsl:apply-templates />  
        </TD>  
      </xsl:template>  
      <xsl:template match="address">  
        <TD>  
          <xsl:apply-templates />  
        </TD>  
      </xsl:template>  
      <xsl:template match="phone">  
        <TD>  
          <xsl:apply-templates />  
        </TD>  
      </xsl:template>  
      <xsl:template match="phone" mode="accountNumber">  
        <xsl:param name="Area_Code"/>  
        <TD STYLE="font-style:italic">  
          1-<xsl:value-of select="."/>-001  
        </TD>  
      </xsl:template>  
    </xsl:stylesheet>  
    ```  
  
2. 커서를 `<xsl:apply-templates select="phone" />` 다음에 놓고 Enter 키를 누릅니다. 그리고 나서 다음 `xsl: apply-templates` 요소 입력을 시작합니다.  
  
    ```  
    <xsl:apply-templates select="phone"  mode="accountNumber">  
    ```  
  
     템플릿 모드의 목록이 `mode=""` 요소의 `xsl:apply-templates` 특성에 나타납니다.  
  
### <a name="to-use-intellisense-in-the-stylesheet-prefix-and-result-prefix-attributes-of-an-xslnamespace-alias-element"></a>xsl:namespace-alias 요소의 stylesheet-prefix 및 result-prefix 특성에 IntelliSense를 사용하려면  
  
1. 새 XSLT 파일을 만들고 다음 코드에 복사합니다.  
  
    ```  
    <xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform" xmlns:alt="http://www.w3.org/1999/XSL/Transform-alternate"  
    version="1.0">  
      <xsl:param name="browser" select="'InternetExplorer'"/>  
      <xsl:template match="/">  
        <alt:stylesheet>  
          <xsl:choose>  
            <xsl:when test="$browser='InternetExplorer'">  
              <alt:import href="IERoutines.xsl"/>  
              <alt:template match="/">  
                <div>  
                  <alt:call-template name="showTable"/>  
                </div>  
              </alt:template>  
            </xsl:when>  
            <xsl:otherwise>  
              <alt:import href="OtherBrowserRoutines.xsl"/>  
              <alt:template match="/">  
                <div>  
                  <alt:call-template name="showTable"/>  
                </div>  
              </alt:template>  
            </xsl:otherwise>  
          </xsl:choose>  
        </alt:stylesheet>  
      </xsl:template>  
    </xsl:stylesheet>  
    ```  
  
2. 커서를 `<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform" xmlns:alt="http://www.w3.org/1999/XSL/Transform-alternate" version="1.0">` 다음에 놓고 Enter 키를 누릅니다. 그리고 나서 다음 `xsl:namespace-alias` 요소 입력을 시작합니다.  
  
    ```  
    <xsl:namespace-alias stylesheet-prefix="alt" result-prefix="xsl"/>  
    ```  
  
     `stylesheet-prefix` 요소의 `result-prefix` 및 `xsl:namespace-alias` 특성에 접미사 목록이 표시되는 방법에 유의해야 합니다.  
  
## <a name="see-also"></a>관련 항목  
 [XML 편집기 IntelliSense 기능](../xml-tools/xml-editor-intellisense-features.md)
