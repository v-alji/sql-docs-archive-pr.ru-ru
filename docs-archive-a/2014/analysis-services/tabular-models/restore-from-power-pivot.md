---
title: Восстановление из PowerPivot | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql11.asvs.ssmsimbi.RestoreFromPP.f1
ms.assetid: 232ac8ed-77fe-47d8-acd3-59bc2fdfdf48
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4dbb0e7867451e67eaa1503c54d7e3da1c276965
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738828"
---
# <a name="restore-from-powerpivot"></a><span data-ttu-id="a8388-102">Восстановление из PowerPivot</span><span class="sxs-lookup"><span data-stu-id="a8388-102">Restore from PowerPivot</span></span>
  <span data-ttu-id="a8388-103">Можно использовать функцию «Восстановление из PowerPivot» в SQL Server Management Studio для создания новой базы данных на основе табличной модели на экземпляре служб Analysis Services (выполняемых в табличном режиме) или восстановления в существующую базу данных из книги PowerPivot (XLSX).</span><span class="sxs-lookup"><span data-stu-id="a8388-103">You can use the Restore from PowerPivot feature in SQL Server Management Studio to create a new Tabular model database on an Analysis Services instance (running in Tabular mode), or restore to an existing database from a PowerPivot workbook (.xlsx).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a8388-104">Шаблон проекта «Импорт из PowerPivot» в SQL Server Data Tools предоставляет аналогичную функциональность.</span><span class="sxs-lookup"><span data-stu-id="a8388-104">The Import from PowerPivot project template in SQL Server Data Tools provides similar functionality.</span></span> <span data-ttu-id="a8388-105">Дополнительные сведения см. [в статье Импорт из PowerPivot &#40;службы SSAS табличные&#41;](import-from-power-pivot-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="a8388-105">For more information, see [Import from PowerPivot &#40;SSAS Tabular&#41;](import-from-power-pivot-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="a8388-106">При использовании восстановления из PowerPivot следует учитывать следующее.</span><span class="sxs-lookup"><span data-stu-id="a8388-106">When using Restore from PowerPivot, keep the following in mind:</span></span>  
  
-   <span data-ttu-id="a8388-107">Чтобы использовать восстановление из PowerPivot, необходимо выполнить вход от имени члена роли администратора сервера для экземпляра служб Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="a8388-107">In order to use Restore from PowerPivot, you must be logged on as a member of the Server Administrators role on the Analysis Services instance.</span></span>  
  
-   <span data-ttu-id="a8388-108">Учетная запись экземпляра служб Analysis Services должна иметь разрешения на чтение файла книги, из которой проводится восстановление.</span><span class="sxs-lookup"><span data-stu-id="a8388-108">The Analysis Services instance service account must have Read permissions on the workbook file you are restoring from.</span></span>  
  
-   <span data-ttu-id="a8388-109">По умолчанию при восстановлении базы данных из PowerPivot свойство «Сведения об олицетворении источника данных» для базы данных на основе табличной модели имеет значение «По умолчанию», что указывает на учетную запись службы для экземпляра служб Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="a8388-109">By default, when you restore a database from PowerPivot, the Tabular model database Data Source Impersonation Info property is set to Default, which specifies the Analysis Services instance service account.</span></span> <span data-ttu-id="a8388-110">Рекомендуется изменить учетные данные олицетворения на учетную запись Windows в свойствах базы данных.</span><span class="sxs-lookup"><span data-stu-id="a8388-110">It is recommended you change the impersonation credentials to a Windows user account in Database Properties.</span></span> <span data-ttu-id="a8388-111">Дополнительные сведения см. в разделе [Олицетворение (табличные службы SSAS)](impersonation-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="a8388-111">For more information, see [Impersonation &#40;SSAS Tabular&#41;](impersonation-ssas-tabular.md).</span></span>  
  
-   <span data-ttu-id="a8388-112">Данные в модели данных PowerPivot копируются в существующую или новую базу данных на основе табличной модели на экземпляре служб Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="a8388-112">Data in the PowerPivot data model will be copied into an existing or new Tabular model database on the Analysis Services instance.</span></span> <span data-ttu-id="a8388-113">Если книга PowerPivot содержит связанные таблицы, они воссоздаются в виде таблиц без источника данных, аналогично таблицам, созданным с использованием вставки в новую таблицу.</span><span class="sxs-lookup"><span data-stu-id="a8388-113">If your PowerPivot workbook contains linked tables, they will be recreated as a table without a data source, similar to a table created using Paste To New table.</span></span>  
  
### <a name="to-restore-from-powerpivot"></a><span data-ttu-id="a8388-114">Восстановление из PowerPivot</span><span class="sxs-lookup"><span data-stu-id="a8388-114">To Restore from PowerPivot</span></span>  
  
1.  <span data-ttu-id="a8388-115">В среде SSMS, в экземпляре Active Directory, в который производится восстановление, щелкните правой кнопкой мыши пункт **Базы данных**и выберите пункт **Восстановление из PowerPivot**.</span><span class="sxs-lookup"><span data-stu-id="a8388-115">In SSMS, in the Active Directory instance you want to restore to, right click **Databases**, and then click **Restore from PowerPivot**.</span></span>  
  
2.  <span data-ttu-id="a8388-116">В диалоговом окне **Восстановление из PowerPivot** в разделе **Источник восстановления**в области **Файл резервной копии**нажмите кнопку **Обзор**и выберите файл ABF или XLSX для восстановления из него.</span><span class="sxs-lookup"><span data-stu-id="a8388-116">In the **Restore from PowerPivot** dialog box, in **Restore Source**, in **Backup file**, click **Browse**, and then select an .abf or .xslx file to restore from.</span></span>  
  
3.  <span data-ttu-id="a8388-117">В поле **Цель восстановления**области **Восстановление базы данных**введите имя новой или существующей базы данных.</span><span class="sxs-lookup"><span data-stu-id="a8388-117">In **Restore Target**, in **Restore database**, type a name for a new database or for an existing database.</span></span> <span data-ttu-id="a8388-118">Если имя не указано, будет использовано имя книги.</span><span class="sxs-lookup"><span data-stu-id="a8388-118">If you do not specify a name, the name of the workbook is used.</span></span>  
  
4.  <span data-ttu-id="a8388-119">В поле **Место хранения**нажмите кнопку **Обзор**и выберите расположение для хранения базы данных.</span><span class="sxs-lookup"><span data-stu-id="a8388-119">In **Storage location**, click **Browse**, and then select a location to store the database.</span></span>  
  
5.  <span data-ttu-id="a8388-120">В области **Параметры**оставьте флажок **Включить сведения о безопасности** .</span><span class="sxs-lookup"><span data-stu-id="a8388-120">In **Options**, leave **Include security information** checked.</span></span> <span data-ttu-id="a8388-121">При восстановлении из книги PowerPivot этот параметр не действует.</span><span class="sxs-lookup"><span data-stu-id="a8388-121">When restoring from a PowerPivot workbook, this setting does not apply.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8388-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="a8388-122">See Also</span></span>  
 <span data-ttu-id="a8388-123">[Табличные модели баз данных &#40;службы SSAS&#41;](tabular-model-databases-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="a8388-123">[Tabular Model Databases &#40;SSAS Tabular&#41;](tabular-model-databases-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="a8388-124">Импорт из табличного&#41;PowerPivot &#40;SSAS</span><span class="sxs-lookup"><span data-stu-id="a8388-124">Import from PowerPivot &#40;SSAS Tabular&#41;</span></span>](import-from-power-pivot-ssas-tabular.md)  
  
  
