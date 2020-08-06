---
title: Запуск Windows PowerShell из среды SQL Server Management Studio | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
ms.assetid: 1f841825-da1f-4062-9a81-3cdbab03845b
author: stevestein
ms.author: sstein
ms.openlocfilehash: e0330e833aaa3344416a31aa700a2b1f6bb4a6e8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658864"
---
# <a name="run-windows-powershell-from-sql-server-management-studio"></a>Запуск Windows PowerShell из среды SQL Server Management Studio
  Можно запускать сеансы Windows PowerShell из **обозревателя объектов** в среде [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]. [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)]запускает Windows PowerShell, загружает `sqlps` модуль и задает контекст пути для связанного узла в дереве **обозревателя объектов** .  
  
## <a name="before-you-begin"></a>Перед началом  
 При указании запуска PowerShell для объекта в **обозревателе объектов** [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] запускается сеанс Windows PowerShell, в котором были [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] загружены и зарегистрированы оснастки PowerShell. Путем для сеанса становится расположение объекта, выбранного правой кнопкой мыши в обозревателе объектов. Например, если щелкнуть правой кнопкой мыши объект базы данных [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] в обозревателе объектов, а затем выбрать команду **Запустить PowerShell**, то путь Windows PowerShell будет иметь следующий вид:  
  
```
SQLSERVER:\SQL\MyComputer\MyInstance\Databases\AdventureWorks2012>  
```  
  
## <a name="to-run-powershell-from-sql-server-management-studio"></a>Запуск PowerShell из среды SQL Server Management Studio 
  
1.  Откройте **Обозреватель объектов**.  
  
2.  Перейдите к узлу для объекта, с которым выполняется работа.  
  
3.  Щелкните объект правой кнопкой мыши и выберите команду **Запустить PowerShell**.  
  
## <a name="permissions"></a>Разрешения  
 При открытии из среды [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)]программа PowerShell не запускается с правами администратора, что может стать причиной того, что некоторые действия не будут выполнены, например вызовы инструментария WMI.  
  
## <a name="see-also"></a>См. также:  
 [SQL Server PowerShell](sql-server-powershell.md)  
