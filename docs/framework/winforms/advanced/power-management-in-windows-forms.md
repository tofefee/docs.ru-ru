---
title: Управление питанием в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- battery states
- power states
ms.assetid: ad04a801-5682-4d88-92c5-26eb9cdb209a
ms.openlocfilehash: 845cc9c910d63dfc7460bba0d5368b5b1e63efcd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33523495"
---
# <a name="power-management-in-windows-forms"></a>Управление питанием в Windows Forms
Приложения Windows Forms можно воспользоваться преимуществами функций управления питанием в операционной системе Windows. Ваши приложения могут отслеживать состояние питания компьютера и предпринять действия, когда происходит изменение состояния. Например если приложение выполняется на портативном компьютере, может потребоваться отключить определенные функции приложения, когда заряд батареи падает ниже определенного уровня.  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Предоставляет <xref:Microsoft.Win32.SystemEvents.PowerModeChanged> событие, возникающее при изменении состояния питания, например, когда пользователь приостанавливает или возобновляет работу операционной системы или при изменении состояния питания от сети или уровня заряда батареи. <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> Свойство <xref:System.Windows.Forms.SystemInformation> класс можно использовать запрос для текущего состояния, как показано в следующем примере кода.  
  
 [!code-csharp[PowerMode#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#1)]
 [!code-vb[PowerMode#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#1)]  
  
 Помимо <xref:System.Windows.Forms.BatteryChargeStatus> перечислений, <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> свойства также содержит перечисления для определения заряда батареи (<xref:System.Windows.Forms.PowerStatus.BatteryFullLifetime%2A>) и процента заряда батареи (<xref:System.Windows.Forms.PowerStatus.BatteryLifePercent%2A>, <xref:System.Windows.Forms.PowerStatus.BatteryLifeRemaining%2A>).  
  
 Можно использовать <xref:System.Windows.Forms.Application.SetSuspendState%2A> метод <xref:System.Windows.Forms.Application> перевести компьютер в спящий режим или режим приостановки. Если `force` аргумента равно `false`, операционная система будет рассылать событие ко всем приложениям, запрашивая разрешение на приостановку. Если `disableWakeEvent` аргумента равно `true`, операционная система отключает все события пробуждения.  
  
 В следующем примере кода показано, как перевод компьютера в спящий режим.  
  
 [!code-csharp[PowerMode#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#2)]
 [!code-vb[PowerMode#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#2)]  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.Win32.SystemEvents.PowerModeChanged>  
 <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>  
 <xref:System.Windows.Forms.Application.SetSuspendState%2A>  
 <xref:Microsoft.Win32.SystemEvents.SessionSwitch>
