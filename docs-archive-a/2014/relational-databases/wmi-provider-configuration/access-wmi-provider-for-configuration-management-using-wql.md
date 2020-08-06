---
title: Доступ к поставщику WMI для управления конфигурацией с помощью WQL | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
helpviewer_keywords:
- query language [WMI]
- WMI Query Language [WMI]
- WQL [WMI]
- WMI Provider for Configuration Management, WQL
ms.assetid: 26499530-d93b-452b-bbe4-217ef1d11e68
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: b58297c5e292ceb18a6e2e50e2b25b9aa352e2fa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654079"
---
# <a name="access-wmi-provider-for-configuration-management-using-wql"></a><span data-ttu-id="f0b8c-102">производить доступ к поставщику WMI для управления конфигурацией с использованием WQL</span><span class="sxs-lookup"><span data-stu-id="f0b8c-102">Access WMI Provider for Configuration Management using WQL</span></span>
  <span data-ttu-id="f0b8c-103">В данном разделе рассматривается способ выполнения инструкций языка WQL [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows применительно к поставщику WMI для управления компьютером.</span><span class="sxs-lookup"><span data-stu-id="f0b8c-103">This section describes how to execute [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Management Instrumentation Query Language (WQL) statements against the WMI Provider for Computer Management.</span></span>  
  
 <span data-ttu-id="f0b8c-104">В этом примере используется редактор языка WQL, WBEMtest.exe, для запуска запросов языка WQL по отношению к поставщику WMI в целях перечисления служб, сетевых протоколов и псевдонимов [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f0b8c-104">The example uses a WQL editor, WBEMtest.exe, to run WQL queries against the WMI Provider to enumerate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services, network protocols, and aliases.</span></span>  
  
### <a name="querying-services-using-wbemtest"></a><span data-ttu-id="f0b8c-105">Запрос служб с помощью WBEMtest</span><span class="sxs-lookup"><span data-stu-id="f0b8c-105">Querying services using WBEMtest</span></span>  
  
1.  <span data-ttu-id="f0b8c-106">В меню **Пуск** выберите пункт **выполнить**, а затем введите `WBEMtest` .</span><span class="sxs-lookup"><span data-stu-id="f0b8c-106">From the **Start** menu, click **Run**, and then enter `WBEMtest`.</span></span>  
  
2.  <span data-ttu-id="f0b8c-107">Откроется диалоговое окно приложения WBEMtest.exe.</span><span class="sxs-lookup"><span data-stu-id="f0b8c-107">The WBEMtest.exe dialog appears.</span></span> <span data-ttu-id="f0b8c-108">Нажмите кнопку **Подключиться**.</span><span class="sxs-lookup"><span data-stu-id="f0b8c-108">Click **Connect**.</span></span>  
  
3.  <span data-ttu-id="f0b8c-109">В первом текстовом поле введите пространство имен поставщика WMI для управления компьютером: root\Microsoft\SqlServer\ComputerManagement11.</span><span class="sxs-lookup"><span data-stu-id="f0b8c-109">In the first text field, type the WMI Provider for Computer Management namespace: root\Microsoft\SqlServer\ComputerManagement11.</span></span> <span data-ttu-id="f0b8c-110">Нажмите кнопку **Подключиться**.</span><span class="sxs-lookup"><span data-stu-id="f0b8c-110">Click **Connect**.</span></span>  
  
4.  <span data-ttu-id="f0b8c-111">Нажмите кнопку **Запрос**.</span><span class="sxs-lookup"><span data-stu-id="f0b8c-111">Click **Query**.</span></span> <span data-ttu-id="f0b8c-112">Введите запрос, который возвращает текущие службы, выполняющиеся на локальном компьютере: **выберите \* из SqlService.**</span><span class="sxs-lookup"><span data-stu-id="f0b8c-112">Type a query that returns the current services running on the local computer: **SELECT \* FROM SqlService.**</span></span> <span data-ttu-id="f0b8c-113">Щелкните **Применить**.</span><span class="sxs-lookup"><span data-stu-id="f0b8c-113">Click **Apply**.</span></span>  
  
5.  <span data-ttu-id="f0b8c-114">Уточните запрос, добавив `WHERE ServiceName = "MSSQLSERVER"`.</span><span class="sxs-lookup"><span data-stu-id="f0b8c-114">Further refine the query by adding `WHERE ServiceName = "MSSQLSERVER"`.</span></span>  
  
  
