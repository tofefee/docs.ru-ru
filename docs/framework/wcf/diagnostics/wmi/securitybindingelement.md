---
title: SecurityBindingElement
ms.date: 03/30/2017
ms.assetid: ef93b6e6-3524-48a8-94d3-c8837f1872f9
author: BrucePerlerMS
ms.openlocfilehash: 19c65b3028ad63b8a78205d00f44cc32322648d5
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/27/2018
ms.locfileid: "47396852"
---
# <a name="securitybindingelement"></a>SecurityBindingElement
SecurityBindingElement  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class SecurityBindingElement : BindingElement  
{  
  string DefaultAlgorithmSuite;  
  boolean IncludeTimestamp;  
  string KeyEntropyMode;  
  LocalServiceSecuritySettings LocalServiceSecuritySettings;  
  string MessageSecurityVersion;  
  string SecurityHeaderLayout;  
};  
```  
  
## <a name="methods"></a>Методы  
 Класс SecurityBindingElement не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  
 Класс SecurityBindingElement имеет следующие свойства.  
  
### <a name="defaultalgorithmsuite"></a>DefaultAlgorithmSuite  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Задает алгоритмы, используемые в сочетании с привязкой.  
  
### <a name="includetimestamp"></a>IncludeTimestamp  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Логическое значение, указывающее, будет ли в каждое сообщение вноситься отметка времени.  
  
### <a name="keyentropymode"></a>KeyEntropyMode  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Источник энтропии, используемый для создания ключей.  
  
### <a name="localservicesecuritysettings"></a>LocalServiceSecuritySettings  
 Тип данных: LocalServiceSecuritySettings  
  
 Тип доступа: только для чтения  
  
 Свойства безопасности для локальной службы, соответствующие данной привязке.  
  
### <a name="messagesecurityversion"></a>MessageSecurityVersion  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Версия, используемая для безопасности сообщения.  
  
### <a name="securityheaderlayout"></a>SecurityHeaderLayout  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Порядок элементов в заголовке безопасности для данной привязки.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Channels.SecurityBindingElement>
