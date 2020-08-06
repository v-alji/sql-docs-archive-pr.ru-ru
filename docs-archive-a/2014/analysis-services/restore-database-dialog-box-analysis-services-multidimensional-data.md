---
title: Диалоговое окно «Восстановление базы данных» (Analysis Services-многомерные данные) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.sqlserverstudio.Restore.f1
ms.assetid: a3990d47-55e2-424e-8eac-87edc937e806
author: minewiskan
ms.author: owend
ms.openlocfilehash: f45a41eb10e81e1cfe1100045cc4d00353cb11fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752424"
---
# <a name="restore-database-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="26edd-102">Диалоговое окно «Восстановление базы данных» (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="26edd-102">Restore Database Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="26edd-103">Диалоговое окно **Восстановление базы данных** используется в среде [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] для восстановления базы данных служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] из файла резервной копии служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] (ABF).</span><span class="sxs-lookup"><span data-stu-id="26edd-103">Use the **Restore Database** dialog box in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to restore an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database from a backup file using the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Backup File (.abf) format.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="26edd-104">Пользователь, выполняющий команду восстановления, должен иметь разрешение на чтение из папки резервного копирования, указанной для каждого восстанавливаемого файла.</span><span class="sxs-lookup"><span data-stu-id="26edd-104">For each backup file, the user who runs the restore command must have permission to read from the backup location specified for each file.</span></span> <span data-ttu-id="26edd-105">Чтобы восстановить базу данных служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , которая не установлена на сервере, пользователь также должен быть членом роли сервера для этого экземпляра служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="26edd-105">To restore an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database that is not installed on the server, the user must also be a member of the server role for that [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance.</span></span> <span data-ttu-id="26edd-106">Чтобы перезаписать базу данных служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , пользователь должен быть членом одной из следующих ролей: роль сервера для экземпляра служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] или роль базы данных с разрешениями "Полный доступ (администратор)" в восстанавливаемой базе данных.</span><span class="sxs-lookup"><span data-stu-id="26edd-106">To overwrite an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database, the user must have one of the following roles: a member of the server role for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance, or a member of a database role with Full Control (Administrator) permissions on the database to be restored.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="26edd-107">После восстановления существующей базы данных пользователь, выполнявший восстановление, может утратить доступ к этой базе данных.</span><span class="sxs-lookup"><span data-stu-id="26edd-107">After restoring an existing database, the user who restored the database might lose access to the restored database.</span></span> <span data-ttu-id="26edd-108">Потеря доступа может произойти в случае, если на время создания резервной копии этот пользователь не был членом роли сервера и роли базы данных с разрешением «Полный доступ (Администратор)».</span><span class="sxs-lookup"><span data-stu-id="26edd-108">This loss of access can occur if, at the time that the backup was performed, the user was not a member of the server role or was not a member of the database role with Full Control (Administrator) permissions.</span></span>  
  
 <span data-ttu-id="26edd-109">**Отображение диалогового окна «Восстановление базы данных»**</span><span class="sxs-lookup"><span data-stu-id="26edd-109">**To display the Restore Database dialog box**</span></span>  
  
-   <span data-ttu-id="26edd-110">В среде [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]щелкните правой кнопкой мыши папку **Базы данных** экземпляра [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] или базу данных в **обозревателе объектов**, а затем выберите **Восстановить**.</span><span class="sxs-lookup"><span data-stu-id="26edd-110">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], right-click either the **Databases** folder of an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance or a database in **Object Explorer**, and then click **Restore**.</span></span>  
  
 <span data-ttu-id="26edd-111">Диалоговое окно **Восстановление базы данных** содержит следующие страницы.</span><span class="sxs-lookup"><span data-stu-id="26edd-111">The **Restore Database** dialog box contains the following pages.</span></span>  
  
## <a name="pages"></a><span data-ttu-id="26edd-112">Страницы</span><span class="sxs-lookup"><span data-stu-id="26edd-112">Pages</span></span>  
 <span data-ttu-id="26edd-113">**Общие**</span><span class="sxs-lookup"><span data-stu-id="26edd-113">**General**</span></span>  
 <span data-ttu-id="26edd-114">Эта страница используется для выбора базы данных, подлежащей восстановлению, файла резервной копии, а также общих параметров и пароля, который будет использоваться для восстановления базы данных.</span><span class="sxs-lookup"><span data-stu-id="26edd-114">Use this page to select the database to restore, the backup file from which to restore the database, as well as the general options and password to use while restoring the database.</span></span> <span data-ttu-id="26edd-115">Дополнительные сведения об этой странице см. в разделе [Общие (диалоговое окно "Восстановление базы данных") (службы Analysis Services — многомерные данные)](general-restore-database-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="26edd-115">For more information about this page, see [General &#40;Restore Database Dialog Box&#41; &#40;Analysis Services - Multidimensional Data&#41;](general-restore-database-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="26edd-116">**Секции**</span><span class="sxs-lookup"><span data-stu-id="26edd-116">**Partitions**</span></span>  
 <span data-ttu-id="26edd-117">Эта страница используется для восстановления локальных секций в заданном расположении и для восстановления удаленных секций из удаленных файлов резервных копий.</span><span class="sxs-lookup"><span data-stu-id="26edd-117">Use this page to restore local partitions to specified locations, and to restore remote partitions from remote backup files.</span></span> <span data-ttu-id="26edd-118">Дополнительные сведения об этой странице см. в разделе [Секции (диалоговое окно "Восстановление базы данных") (службы Analysis Services — многомерные данные)](partitions-restore-database-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="26edd-118">For more information about this page, see [Partitions &#40;Restore Database Dialog Box&#41; &#40;Analysis Services - Multidimensional Data&#41;](partitions-restore-database-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26edd-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="26edd-119">See Also</span></span>  
 <span data-ttu-id="26edd-120">[Analysis Services конструкторов и диалоговых окон &#40;многомерных данных&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="26edd-120">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="26edd-121">Создание и восстановление резервных копий баз данных служб Analysis Services</span><span class="sxs-lookup"><span data-stu-id="26edd-121">Backup and Restore of Analysis Services Databases</span></span>](multidimensional-models/backup-and-restore-of-analysis-services-databases.md)  
  
  
