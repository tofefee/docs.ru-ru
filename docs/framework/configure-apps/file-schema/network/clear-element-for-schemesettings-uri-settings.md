---
title: '&lt;Очистить&gt; элемент для schemeSettings (параметры Uri)'
ms.date: 03/30/2017
ms.assetid: 65098332-ce61-4542-ab8d-e7dc0257d31f
author: mcleblanc
ms.author: markl
ms.openlocfilehash: f0daa689ba09fa39ffe0f38d769112f0f095592a
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2018
ms.locfileid: "48028044"
---
# <a name="ltcleargt-element-for-schemesettings-uri-settings"></a>&lt;Очистить&gt; элемент для schemeSettings (параметры Uri)
Удаляет все существующие параметры схемы.  
  
 \<configuration>  
\<URI >  
\<schemeSettings >  
\<Очистить >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Отсутствует.  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[Элемент \<schemeSettings> (параметры URI)](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|Определяет, как <xref:System.Uri> анализируется для определенных схем.|  
  
## <a name="remarks"></a>Примечания  
 По умолчанию <xref:System.Uri?displayProperty=nameWithType> знаком процента Отмена переходов класс разделители пути до выполнения сжатия пути. Это было реализовано в качестве механизма защиты от атак, следующим образом:  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 Если этот URI передается вниз, чтобы модули не обрабатывает процентов символы в кодировке неправильно, это может привести в следующей команде, выполняемой на сервере:  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 По этой причине <xref:System.Uri?displayProperty=nameWithType> класса первый разделители пути Отмена переходов, а затем применяет сжатие пути. Результат передачи вредоносных URL-адрес выше <xref:System.Uri?displayProperty=nameWithType> класса конструктор результаты в следующий URI:  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 Можно изменить это поведение по умолчанию для не разделители отмены escape процента закодированный путь, с помощью параметра конфигурации schemeSettings для определенной схемы.  
  
## <a name="configuration-files"></a>Файлы конфигурации  
 Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).  
  
## <a name="example"></a>Пример  
 В следующем примере показано конфигурацию, используемую <xref:System.Uri> класс, который удаляет все параметры схемы, а затем добавляет поддержку не экранирования разделителей закодированные пути для схемы http.  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <clear/>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>  
 <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>  
 <xref:System.GenericUriParserOptions?displayProperty=nameWithType>  
 <xref:System.Uri?displayProperty=nameWithType>  
 [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
