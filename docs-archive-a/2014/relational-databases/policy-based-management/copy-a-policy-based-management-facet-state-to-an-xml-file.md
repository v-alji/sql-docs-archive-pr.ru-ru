---
title: Копирование состояния аспекта управления на основе политик в XML-файл | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, copy facet state to XML file
ms.assetid: 7d604ab1-6dd6-4f8e-a79c-eba99ab106fd
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7be2332d9a2507a079d85a3424bda3a387609ca7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731518"
---
# <a name="copy-a-policy-based-management-facet-state-to-an-xml-file"></a><span data-ttu-id="149e8-102">Копирование состояния аспекта управления на основе политик в XML-файл</span><span class="sxs-lookup"><span data-stu-id="149e8-102">Copy a Policy-Based Management Facet State to an XML File</span></span>
  <span data-ttu-id="149e8-103">В этом разделе описывается копирование состояния аспекта управления на основе политик в XML-файл в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="149e8-103">This topic describes how to how to copy the state of a Policy-Based Management facet to an XML file in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="149e8-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="149e8-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="149e8-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="149e8-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="149e8-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="149e8-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="149e8-107">**Копирование состояния аспекта в XML-файл с помощью:**</span><span class="sxs-lookup"><span data-stu-id="149e8-107">**To copy a facet state to an XML file, using:**</span></span>  
  
     [<span data-ttu-id="149e8-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="149e8-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="149e8-109">Перед началом</span><span class="sxs-lookup"><span data-stu-id="149e8-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="149e8-110">безопасность</span><span class="sxs-lookup"><span data-stu-id="149e8-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="149e8-111">Permissions</span><span class="sxs-lookup"><span data-stu-id="149e8-111">Permissions</span></span>  
 <span data-ttu-id="149e8-112">Для процедуры в этом разделе требуется членство в роли PolicyAdministratorRole базы данных msdb.</span><span class="sxs-lookup"><span data-stu-id="149e8-112">The procedures in this topic require membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="149e8-113">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="149e8-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-copy-a-facet-state-to-an-xml-file"></a><span data-ttu-id="149e8-114">Копирование состояния аспекта в XML-файл</span><span class="sxs-lookup"><span data-stu-id="149e8-114">To copy a facet state to an XML file</span></span>  
  
1.  <span data-ttu-id="149e8-115">В обозревателе объектов щелкните правой кнопкой мыши экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], объект экземпляра, базу данных или объект базы данных и выберите команду **Аспекты**.</span><span class="sxs-lookup"><span data-stu-id="149e8-115">In Object Explorer, right-click an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], instance object, database, or database object, and then click **Facets**.</span></span>  
  
2.  <span data-ttu-id="149e8-116">В диалоговом окне **Просмотр аспектов —**_имя_объекта_ щелкните **Экспортировать текущее состояние как политику**.</span><span class="sxs-lookup"><span data-stu-id="149e8-116">In the **View Facets -**_object_name_ dialog box, click **Export Current State as Policy**.</span></span>  
  
3.  <span data-ttu-id="149e8-117">Введите имя и путь к файлу в диалоговом окне **Экспортировать как политику** либо найдите файл при помощи кнопки "Обзор" (**...**) и введите имя XML-файла.</span><span class="sxs-lookup"><span data-stu-id="149e8-117">In the **Export as Policy** dialog box, type the path and name of the file; or use the Browse (**...**) button to locate the file, and then type the name of the XML file.</span></span> <span data-ttu-id="149e8-118">Дополнительные сведения о доступных параметрах данного диалогового окна см. в разделе [Export As Policy Dialog Box](export-as-policy-dialog-box.md)</span><span class="sxs-lookup"><span data-stu-id="149e8-118">For more information on the available options in this dialog box, see [Export As Policy Dialog Box](export-as-policy-dialog-box.md)</span></span>  
  
4.  <span data-ttu-id="149e8-119">После завершения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="149e8-119">When finished, click **OK**.</span></span>  
  
  
