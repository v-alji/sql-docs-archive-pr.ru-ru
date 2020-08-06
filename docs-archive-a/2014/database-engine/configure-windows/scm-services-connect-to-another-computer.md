---
title: Подключение к другому компьютеру (диспетчер конфигурации SQL Server) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- connections [SQL Server], other computers
ms.assetid: c4c1e94f-4f5f-431e-8b5b-d5ff97baf723
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f3d478cebc1ca36ccb8f87b0355b7c8fe0a928cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669106"
---
# <a name="connect-to-another-computer-sql-server-configuration-manager"></a>Подключение к другому компьютеру (диспетчер конфигурации SQL Server)
  В этом разделе описывается подключение к другому компьютеру в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]. Выполните первую процедуру, чтобы открыть консоль управления [!INCLUDE[msCoName](../../includes/msconame-md.md)] «Управление компьютером», подключитесь к компьютеру и разверните дерево «Службы и приложения». Выполните вторую процедуру для создания файла с ссылкой на диспетчер конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на удаленном компьютере.  
  
> [!NOTE]  
>  Некоторые действия не могут выполняться с помощью Configuration Manager при удаленном подключении.  
  
 Для запуска, остановки и приостановки служб на другом компьютере можно также подключиться к этому серверу при помощи среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], щелкнуть правой кнопкой мыши этот сервер или агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , затем выбрать нужное действие.  
  
##  <a name="SSMSProcedure"></a>  
  
#### <a name="to-connect-to-another-computer-with-windows-computer-management"></a>Подключение к другому компьютеру с помощью управления компьютерами Windows  
  
1.  В меню **Пуск** щелкните правой кнопкой мыши **Мой компьютер**, а затем выберите **Управление**.  
  
2.  В диалоговом окне **Управление компьютером**щелкните правой кнопкой мыши **Управление компьютером (локальным)**, а затем нажмите **Подключиться к другому компьютеру**.  
  
3.  В диалоговом окне **Выбор компьютера** , в текстовом поле **Другой компьютер** введите имя компьютера, которым нужно управлять, а затем нажмите кнопку **ОК**.  
  
     Управление компьютером отображает службы, выполняющиеся на удаленном компьютере. Узел верхнего уровня сменится на **Управление компьютером** \<*remotecomputer*>.  
  
4.  В дереве консоли разверните **Службы и приложения**, затем разверните **Диспетчер конфигурации SQL Server** для управления службами удаленного компьютера.  
  
#### <a name="to-save-a-link-to-sql-server-configuration-manager-for-another-computer"></a>Сохранение ссылки на диспетчер конфигурации SQL Server для другого компьютера  
  
1.  В меню **Пуск** выберите команду **Выполнить**.  
  
2.  В поле **Открыть** введите, `mmc -a` чтобы открыть [!INCLUDE[msCoName](../../includes/msconame-md.md)] консоль управления в режиме автора.  
  
3.  В меню **Файл** выберите **Добавить или удалить оснастку**.  
  
4.  В диалоговом окне **Добавить или удалить оснастку** нажмите кнопку **Добавить**.  
  
5.  В диалоговом окне **Добавить изолированную оснастку** выберите **Управление компьютером** и нажмите кнопку **Добавить**.  
  
6.  В диалоговом окне **Управление компьютером** выберите **Другой компьютер**, введите имя компьютера, которым нужно управлять и нажмите кнопку **Готово**.  
  
7.  В диалоговом окне **Добавить изолированную оснастку** нажмите кнопку **Закрыть**.  
  
8.  В диалоговом окне **Добавить или удалить оснастку** нажмите кнопку **ОК**.  
  
9. Разверните узел **Управление компьютером ( ***\<computer name>*** )**, а затем **службы и приложения**.  
  
10. Щелкните правой кнопкой мыши **Диспетчер конфигурации SQL Server**, затем щелкните **Новое окно отсюда**.  
  
11. В меню **Окно** выберите **Корень консоли**, чтобы вернуться в первое окно, и удалите его.  
  
12. В меню **файл** выберите команду **Сохранить как**и сохраните файл в нужной папке с соответствующим именем с `.msc` расширением файла. Закройте консоль управления (MMC) [!INCLUDE[msCoName](../../includes/msconame-md.md)] .  
  
13. Чтобы открыть диспетчер конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на целевом компьютере, дважды щелкните этот файл. При желании сохраните ссылку на этот файл на рабочем столе или в меню **Пуск** .  
  
> [!CAUTION]  
>  При использовании диспетчера конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на удаленном компьютере имя компьютера не является очевидным, и можно по ошибке остановить или настроить не тот компьютер. На вкладке **Служба** в поле **Имя узла** проверьте имя компьютера перед тем, как изменять службу.  
  
## <a name="see-also"></a>См. также:  
 [Настройка инструментария WMI для отображения состояния сервера в инструментальных средствах SQL Server](../../ssms/configure-wmi-to-show-server-status-in-sql-server-tools.md)  
  
  