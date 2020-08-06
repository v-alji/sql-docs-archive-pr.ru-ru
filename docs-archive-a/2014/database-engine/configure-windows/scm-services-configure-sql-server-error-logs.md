---
title: Настройка журналов ошибок SQL Server | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.configurelogs.configureerrorlogs.f1
ms.assetid: 03f0d463-9b0b-4af9-a853-da936d75e5af
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8acc27150f42049384e2789ef83ae66a737da9bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669109"
---
# <a name="configure-sql-server-error-logs"></a><span data-ttu-id="6453f-102">Настройка журналов ошибок SQL Server</span><span class="sxs-lookup"><span data-stu-id="6453f-102">Configure SQL Server Error Logs</span></span>
  <span data-ttu-id="6453f-103">В этом разделе описано, как просмотреть и изменить способ очистки журналов ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6453f-103">This topic describes how to view or modify the way [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error logs are recycled.</span></span>  
  
## <a name="to-open-the-configure-sql-server-error-logs-dialog-box"></a><span data-ttu-id="6453f-104">Открытие диалогового окна «Настройка журналов ошибок SQL Server»</span><span class="sxs-lookup"><span data-stu-id="6453f-104">To open the Configure SQL Server Error Logs dialog box</span></span>  
  
1.  <span data-ttu-id="6453f-105">В обозревателе объектов разверните экземпляр SQL Server, раскройте узел **Управление**, щелкните правой кнопкой мыши **Журналы SQL Server**, а затем выберите пункт **Настройка**.</span><span class="sxs-lookup"><span data-stu-id="6453f-105">In Object Explorer, expand the instance of SQL Server, expand **Management**, right-click **SQL Server Logs**, and then click **Configure**.</span></span>  
  
2.  <span data-ttu-id="6453f-106">В диалоговом окне **Настройка журналов ошибок SQL Server** выберите один из следующих параметров.</span><span class="sxs-lookup"><span data-stu-id="6453f-106">In the **Configure SQL Server Error Logs** dialog box, choose from the following options.</span></span>  
  
     <span data-ttu-id="6453f-107">**Ограничить количество файлов журнала ошибок перед очисткой**</span><span class="sxs-lookup"><span data-stu-id="6453f-107">**Limit the number of the error log files before they are recycled**</span></span>  
     <span data-ttu-id="6453f-108">Установите этот флажок, чтобы ограничить количество файлов журнала ошибок, создаваемых до их очистки.</span><span class="sxs-lookup"><span data-stu-id="6453f-108">Check to limit the number of error logs created before they are recycled.</span></span> <span data-ttu-id="6453f-109">При каждом запуске экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] создается новый журнал ошибок.</span><span class="sxs-lookup"><span data-stu-id="6453f-109">A new error log is created each time an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is started.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="6453f-110">сохраняет резервные копии шести предыдущих журналов, если этот флажок не установлен и ниже не указано иное максимальное число файлов журнала ошибок.</span><span class="sxs-lookup"><span data-stu-id="6453f-110">retains backups of the previous six logs, unless you check this option, and specify a different maximum number of error log files below.</span></span>  
  
     <span data-ttu-id="6453f-111">**Максимальное количество файлов журналов ошибок**</span><span class="sxs-lookup"><span data-stu-id="6453f-111">**Maximum number of error log files**</span></span>  
     <span data-ttu-id="6453f-112">Укажите максимальное количество файлов журнала ошибок, создаваемых до их очистки.</span><span class="sxs-lookup"><span data-stu-id="6453f-112">Specify the maximum number of error log files created before they are recycled.</span></span> <span data-ttu-id="6453f-113">Значение по умолчанию — 6, то есть [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] сохраняет шесть предыдущих резервных копий журналов до их очистки.</span><span class="sxs-lookup"><span data-stu-id="6453f-113">The default is 6, which is the number of previous backup logs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] retains before recycling them.</span></span>  
  
  
