---
title: Создание интернет-запросов
ms.date: 03/30/2017
helpviewer_keywords:
- WebRequest class, sending and receiving data
- Networking
- HttpWebResponse class, sending and receiving data
- requesting data from Internet, creating requests
- Network Resources
- Internet, requesting data
- data requests, creating requests
ms.assetid: faab683e-3f1e-4eee-b5e9-59f7245033d5
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 201bc5e92aeedcbfe2f710681cf3bbc773a11424
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/26/2018
ms.locfileid: "47193386"
---
# <a name="creating-internet-requests"></a>Создание интернет-запросов
Приложения создают экземпляры <xref:System.Net.WebRequest> с помощью метода <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType>. Этот статический метод создает класс, производный от **WebRequest**, на основе переданной ему схемы URI.  
  
## <a name="web-file-and-ftp-requests"></a>Запросы Web, File и FTP  
 На платформе .NET Framework представлен класс <xref:System.Net.HttpWebRequest>, который является производным от **WebRequest** и обеспечивает обработку запросов HTTP и HTTPS. В большинстве случаев класс **WebRequest** предоставляет все свойства, необходимые для выполнения запроса. Тем не менее при необходимости вы можете приводить объекты **WebRequest**, созданные методом **WebRequest.Create**, к типу **HttpWebRequest** для доступа к свойствам запроса, относящимся к протоколу HTTP. Аналогичным образом, объект **HttpWebResponse** обрабатывает ответы на запросы HTTP и HTTPS. Для доступа к свойствам объекта **HttpWebResponse**, относящимся к протоколу HTTP, необходимо привести объекты **WebResponse** к типу **HttpWebResponse**.  
  
 Платформа .NET Framework также предоставляет классы <xref:System.Net.FileWebRequest> и <xref:System.Net.FileWebResponse> для обработки запросов ресурсов, использующих схему URI "file:". Аналогичным образом, классы <xref:System.Net.FtpWebRequest> и <xref:System.Net.FtpWebResponse> используются для обработки запросов ресурсов, использующих схему "ftp:". Если вы выполняете запросы к ресурсу, использующему любую из этих схем, то можете получить объект, с помощью которого будет выполняться запрос, используя метод **WebRequest.Create**.  
  
 Для обработки запросов, использующих другие протоколы уровня приложений, необходимо реализовать классы для определенного протокола, производные от **WebRequest** и **WebResponse**. Дополнительные сведения см. в разделе [Программирование подключаемых протоколов](../../../docs/framework/network-programming/programming-pluggable-protocols.md).  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Запрос данных с помощью класса WebRequest](../../../docs/framework/network-programming/how-to-request-data-using-the-webrequest-class.md)  
 [Запрос данных](../../../docs/framework/network-programming/requesting-data.md)
