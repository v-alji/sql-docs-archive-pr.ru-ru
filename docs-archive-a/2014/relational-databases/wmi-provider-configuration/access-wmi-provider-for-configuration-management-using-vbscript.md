---
title: Изменение дополнительных свойств SQL Serverной службы с помощью VBScript | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- VBScript [WMI]
- modifying SQL Server Service properties
- WMI Provider for Configuration Management, VBScript
ms.assetid: f3c5d981-eaa3-4d34-9b91-37e42636aa81
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 2cf722b00a31723b77624c33fef81a82ff0cb926
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668675"
---
# <a name="modify-sql-server-service-advanced-properties-using-vbscript"></a><span data-ttu-id="c001a-102">изменить расширенные свойства службы SQL Server с помощью VBScript</span><span class="sxs-lookup"><span data-stu-id="c001a-102">Modify SQL Server Service Advanced Properties using VBScript</span></span>
  <span data-ttu-id="c001a-103">В этом разделе описывается создание программы VBScript, которая содержит версию установленных экземпляров [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , работающих на компьютере.</span><span class="sxs-lookup"><span data-stu-id="c001a-103">This section describes how to create a VBScript program that lists the version of installed instances of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are running on a computer.</span></span>  
  
 <span data-ttu-id="c001a-104">В этом примере кода перечисляются экземпляры [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], запущенные на компьютере, и их версии.</span><span class="sxs-lookup"><span data-stu-id="c001a-104">The code example lists the instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running on the computer and its version.</span></span>  
  
### <a name="listing-name-and-version-of-installed-instances-of-sql-server"></a><span data-ttu-id="c001a-105">Список имен и версий установленных экземпляров SQL Server</span><span class="sxs-lookup"><span data-stu-id="c001a-105">Listing name and version of installed instances of SQL Server</span></span>  
  
1.  <span data-ttu-id="c001a-106">Откройте новый документ в текстовом редакторе, например в [!INCLUDE[msCoName](../../includes/msconame-md.md)] блокноте.</span><span class="sxs-lookup"><span data-stu-id="c001a-106">Open a new document in a text editor, such as [!INCLUDE[msCoName](../../includes/msconame-md.md)] Notepad.</span></span> <span data-ttu-id="c001a-107">Скопируйте код, который следует за данной процедурой, и сохраните файл с расширением VBS.</span><span class="sxs-lookup"><span data-stu-id="c001a-107">Copy the code that follows this procedure and save the file with a .vbs extension.</span></span> <span data-ttu-id="c001a-108">Этот пример называется test.vbs.</span><span class="sxs-lookup"><span data-stu-id="c001a-108">This example is called test.vbs.</span></span>  
  
2.  <span data-ttu-id="c001a-109">Подключитесь к экземпляру поставщика WMI при помощи функции `GetObject` языка VBScript.</span><span class="sxs-lookup"><span data-stu-id="c001a-109">Connect to an instance of the WMI Provider for Computer Management with the VBScript `GetObject` function.</span></span> <span data-ttu-id="c001a-110">В данном примере выполняется подключение к удаленному компьютеру с именем mpc, но не указывается имя компьютера для подключения к локальному компьютеру: winmgmts:root\Microsoft\SqlServer\ComputerManagement.</span><span class="sxs-lookup"><span data-stu-id="c001a-110">This example connects to a remote computer named mpc, but omit the computer name to connect to the local computer: winmgmts:root\Microsoft\SqlServer\ComputerManagement.</span></span> <span data-ttu-id="c001a-111">Дополнительные сведения о функции `GetObject` см. в справочнике по VBScript.</span><span class="sxs-lookup"><span data-stu-id="c001a-111">For more information about the `GetObject` function, see the VBScript reference.</span></span>  
  
3.  <span data-ttu-id="c001a-112">Метод `InstancesOf` используется для перечисления списка служб.</span><span class="sxs-lookup"><span data-stu-id="c001a-112">Use the `InstancesOf` method to enumerate a list of the services.</span></span> <span data-ttu-id="c001a-113">Вместо метода `ExecQuery` службы можно перечислить при помощи простого WQL-запроса и метода `InstancesOf`.</span><span class="sxs-lookup"><span data-stu-id="c001a-113">The services can also be enumerated by using a simple WQL query and an `ExecQuery` method instead of the `InstancesOf` method.</span></span>  
  
4.  <span data-ttu-id="c001a-114">Воспользуйтесь методами `ExecQuery` и WQL-запросом для доступа к именам и версиям установленных экземпляров [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c001a-114">Use the `ExecQuery` method and a WQL query to retrieve the name and version of the installed instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
5.  <span data-ttu-id="c001a-115">Сохраните файл.</span><span class="sxs-lookup"><span data-stu-id="c001a-115">Save the file.</span></span>  
  
6.  <span data-ttu-id="c001a-116">Запустите сценарий, введя `cscript test.vbs` в командной строке.</span><span class="sxs-lookup"><span data-stu-id="c001a-116">Run the script by typing `cscript test.vbs` at the command prompt.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c001a-117">Пример</span><span class="sxs-lookup"><span data-stu-id="c001a-117">Example</span></span>  
  
```  
set wmi = GetObject("WINMGMTS:\\.\root\Microsoft\SqlServer\ComputerManagement12")  
for each prop in wmi.ExecQuery("select * from SqlServiceAdvancedProperty where SQLServiceType = 1 AND PropertyName = 'VERSION'")  
WScript.Echo prop.ServiceName & " " & prop.PropertyName & ": " & prop.PropertyStrValue  
next  
```  
  
  
