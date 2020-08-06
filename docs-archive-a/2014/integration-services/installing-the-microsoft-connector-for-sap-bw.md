---
title: Установка соединителя Microsoft для 1,1 SAP BW | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 3bfb9023-9597-4f59-9085-4b9057e7702e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0ef96f38054f04e71de72bda0bbb12f8f003ef20
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658898"
---
# <a name="installing-the-microsoft-connector-for-11-sap-bw"></a><span data-ttu-id="f2771-102">Установка Microsoft Connector 1.1 для SAP BW</span><span class="sxs-lookup"><span data-stu-id="f2771-102">Installing the Microsoft Connector for 1.1 SAP BW</span></span>
  <span data-ttu-id="f2771-103">Чтобы установить [!INCLUDE[msCoName](../includes/msconame-md.md)] соединитель 1,1 для SAP BW и его документацию, скачайте и запустите пакет установщика Windows на веб-странице SQL Server пакета дополнительных компонентов.</span><span class="sxs-lookup"><span data-stu-id="f2771-103">To install the [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW and its documentation, download and run the Windows installer package from the SQL Server Feature Pack Web page.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f2771-104">Документация по Microsoft Connector 1.1 для SAP BW предполагает, что читатель знаком со средой SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="f2771-104">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="f2771-105">Дополнительные сведения о SAP Netweaver BW или сведения о настройке объектов и процессов SAP Netweaver BW см. в документации SAP.</span><span class="sxs-lookup"><span data-stu-id="f2771-105">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f2771-106">Для извлечения данных из SAP Netweaver BW требуется дополнительная лицензия SAP.</span><span class="sxs-lookup"><span data-stu-id="f2771-106">Extracting data from SAP Netweaver BW requires additional SAP licensing.</span></span> <span data-ttu-id="f2771-107">Обратитесь к SAP, чтобы уточнить требования.</span><span class="sxs-lookup"><span data-stu-id="f2771-107">Check with SAP to verify these requirements.</span></span>  
  
## <a name="required-sap-files"></a><span data-ttu-id="f2771-108">Необходимые файлы SAP</span><span class="sxs-lookup"><span data-stu-id="f2771-108">Required SAP Files</span></span>  
 <span data-ttu-id="f2771-109">Чтобы использовать [!INCLUDE[msCoName](../includes/msconame-md.md)] соединитель 1,1 для SAP BW, не нужно устанавливать клиентское программное обеспечение SAP (графический интерфейс SAP) на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="f2771-109">To use the [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW, you do not have to install the SAP Front End software (SAP GUI) on the local computer.</span></span>  
  
 <span data-ttu-id="f2771-110">Однако необходимо скопировать файл соединителя SAP .NET (librfc32.dll) во вложенную папку в системном каталоге Windows.</span><span class="sxs-lookup"><span data-stu-id="f2771-110">However you must copy the SAP .NET connector file, librfc32.dll, into the system subfolder in the Windows folder.</span></span> <span data-ttu-id="f2771-111">(Обычно это каталог **C:\Windows\system32**.)</span><span class="sxs-lookup"><span data-stu-id="f2771-111">(Typically, this folder location is **C:\Windows\system32**.)</span></span>  
  
## <a name="considerations-for-64-bit-computers"></a><span data-ttu-id="f2771-112">Замечания для 64-разрядных компьютеров</span><span class="sxs-lookup"><span data-stu-id="f2771-112">Considerations for 64-bit Computers</span></span>  
 <span data-ttu-id="f2771-113">[!INCLUDE[msCoName](../includes/msconame-md.md)]Соединитель 1,1 для SAP BW полностью поддерживает 64-разрядную версию [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="f2771-113">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW fully supports the 64-bit version of [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows.</span></span> <span data-ttu-id="f2771-114">На 64-разрядном компьютере [!INCLUDE[msCoName](../includes/msconame-md.md)] соединитель 1,1 для SAP BW имеет следующие дополнительные требования:</span><span class="sxs-lookup"><span data-stu-id="f2771-114">On a 64-bit computer, the [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW has the following additional requirements:</span></span>  
  
-   <span data-ttu-id="f2771-115">Для запуска пакетов в 64-разрядном режиме в любой 64-разрядной ОС Windows скопируйте 64-разрядную версию файла графического пользовательского интерфейса SAP librfc32.dll в папку **system32** в каталоге Windows.</span><span class="sxs-lookup"><span data-stu-id="f2771-115">To run packages in 64-bit mode on any 64-bit Windows operating system, copy the 64-bit version of the SAP GUI file, librfc32.dll, into the **system32** folder of the Windows folder.</span></span> <span data-ttu-id="f2771-116">(Обычно это каталог **C:\Windows\system32**.)</span><span class="sxs-lookup"><span data-stu-id="f2771-116">(Typically, this file location is **C:\Windows\system32**.)</span></span>  
  
-   <span data-ttu-id="f2771-117">Для запуска пакетов в 32-разрядном режиме в любой 64-разрядной ОС Windows скопируйте файл графического пользовательского интерфейса SAP librfc32.dll в папку **SysWow64** в каталоге Windows.</span><span class="sxs-lookup"><span data-stu-id="f2771-117">To run packages in 32-bit mode on any 64-bit Windows operating system, copy the SAP GUI file, librfc32.dll, into the **SysWow64** folder of the Windows folder.</span></span> <span data-ttu-id="f2771-118">(Обычно это каталог **C:\Windows\SysWow64**.)</span><span class="sxs-lookup"><span data-stu-id="f2771-118">(Typically, this folder location is **C:\Windows\SysWow64**.)</span></span>  
  
  
