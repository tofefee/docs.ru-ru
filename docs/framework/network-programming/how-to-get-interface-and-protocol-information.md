---
title: Практическое руководство. Получение информации об интерфейсах и протоколах
ms.date: 03/30/2017
helpviewer_keywords:
- Network
ms.assetid: fd88d26c-4063-495e-a253-736ac3e6b23f
author: mcleblanc
ms.author: markl
ms.openlocfilehash: ae4eb38c72a7f7629cea0f8137a4337553457808
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/26/2018
ms.locfileid: "47200910"
---
# <a name="how-to-get-interface-and-protocol-information"></a>Практическое руководство. Получение информации об интерфейсах и протоколах
В этом примере показано, как считать статистику TCP сетевого интерфейса.  
  
## <a name="example"></a>Пример  
  
```  
public static void ShowTcpStatistics(NetworkInterfaceComponent version)  
{  
    IPGlobalProperties properties =  
          IPGlobalProperties.GetIPGlobalProperties();  
    TcpStatistics tcpstat = null;  
    Console.WriteLine("");  
    switch (version)  
    {  
        case NetworkInterfaceComponent.IPv4:  
             tcpstat = properties.GetTcpIPv4Statistics();  
            Console.WriteLine("TCP/IPv4 Statistics:");  
            break;  
        case NetworkInterfaceComponent.IPv6:  
            tcpstat = properties.GetTcpIPv6Statistics();  
            Console.WriteLine("TCP/IPv6 Statistics:");  
            break;  
        default:  
            throw new ArgumentException("version");  
            break;  
    }  
    Console.WriteLine("  Minimum Transmission Timeout. : {0}",   
        tcpstat.MinimumTransmissionTimeout);  
    Console.WriteLine("  Maximum Transmission Timeout. : {0}",   
        tcpstat.MaximumTransmissionTimeout);  
  
    Console.WriteLine("  Connection Data:");  
    Console.WriteLine("      Current : {0}",   
    tcpstat.CurrentConnections);  
    Console.WriteLine("      Cumulative : {0}",   
        tcpstat.CumulativeConnections);  
    Console.WriteLine("      Initiated  : {0}",   
        tcpstat.ConnectionsInitiated);  
    Console.WriteLine("      Accepted : {0}",   
        tcpstat.ConnectionsAccepted);  
    Console.WriteLine("      Failed Attempts : {0}",   
        tcpstat.FailedConnectionAttempts);  
    Console.WriteLine("      Reset : {0}",   
        tcpstat.ResetConnections);  
  
    Console.WriteLine("");  
    Console.WriteLine("  Segment Data:");  
    Console.WriteLine("      Received  ................... : {0}",   
        tcpstat.SegmentsReceived);  
    Console.WriteLine("      Sent : {0}",   
        tcpstat.SegmentsSent);  
    Console.WriteLine("      Retransmitted : {0}",   
        tcpstat.SegmentsResent);  
  
    Console.WriteLine("");  
}  
```  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   Ссылки на пространство имен **System.Net**.
