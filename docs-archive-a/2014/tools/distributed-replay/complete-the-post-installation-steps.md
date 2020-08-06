---
title: Выполните действия после установки | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: 0a788a2a-9b4f-4bfc-b1b5-83eeb1ea9ab2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 1e9aae3dccaa409bcebc473213286f3edf19e7f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665175"
---
# <a name="complete-the-post-installation-steps"></a>Выполнение действий после установки
  После установки компонента распределенного воспроизведения следует изменить учетные записи служб клиента и контроллера распределенного воспроизведения.  
  
### <a name="to-complete-the-post-installation-steps"></a>Выполнение действий после установки  
  
1.  **Создание правил брандмауэра**. На компьютерах контроллера и клиента в брандмауэре необходимо разрешить входящий трафик для соответствующей службы. Укажите правила брандмауэра для исполняемых файлов службы, расположенных в установочных папках.  
  
    1.  Для службы контроллера создайте правило для файла **DReplayController.exe**, расположенного в папке установки. Например, следующая команда включает это правило, где `%InstallPath%` — папка установки службы:  
  
         `netsh advfirewall firewall add rule name="allow dreplay controller" dir=in program="%InstallPath%\DReplayController\DReplayController.exe" action=allow`  
  
    2.  Для службы клиента на каждом клиентском компьютере создайте правило для файла **DReplayClient.exe**, расположенного в папке установки. Например, следующая команда включает это правило, где `%InstallPath%` — папка установки службы:  
  
         `netsh advfirewall firewall add rule name="allow dreplay client" dir=in program="%InstallPath%\DReplayClient\DReplayClient.exe" action=allow`  
  
2.  **Предоставьте каждому клиенту разрешения на целевом сервере**. После завершения установки службы клиента на клиентских компьютерах следует вручную добавить учетные записи службы клиента в роль системного администратора на целевом экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
## <a name="net-framework-security"></a>Безопасность .NET Framework  
 Для установки компонентов распределенного воспроизведения необходимо обладать разрешениями администратора. Только имя входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с разрешениями sysadmin может добавлять учетные записи службы клиента в роль sysadmin тестового сервера. Дополнительные сведения о вопросах безопасности распределенного воспроизведения см. в разделе [Distributed Replay Security](distributed-replay-security.md).  
  
  
