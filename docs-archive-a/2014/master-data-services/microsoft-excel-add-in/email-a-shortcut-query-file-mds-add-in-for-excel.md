---
title: Отправка файла ярлыка запроса по электронной почте (надстройка MDS для Excel) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 5d46f20a-b04a-45c7-82af-02a2baaabbd7
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c6474e6213ce67b31b0ea52eb548fab19562f438
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731805"
---
# <a name="email-a-shortcut-query-file-mds-add-in-for-excel"></a><span data-ttu-id="07521-102">Отправка файла ярлыка запроса по электронной почте (надстройка MDS для Excel)</span><span class="sxs-lookup"><span data-stu-id="07521-102">Email a Shortcut Query File (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="07521-103">В [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] можно отправить кому-либо файл ярлыка запроса по электронной почте, если адресат должен иметь возможность работать с теми же данными, что и вы.</span><span class="sxs-lookup"><span data-stu-id="07521-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], email a shortcut query file to someone when you want to ensure they're working with the same data that you are.</span></span> <span data-ttu-id="07521-104">Вместо сохранения и отправки листа по электронной почте следует предоставлять общий доступ к запросу.</span><span class="sxs-lookup"><span data-stu-id="07521-104">You should share queries rather than saving the worksheet and emailing it.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="07521-105">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="07521-105">Prerequisites</span></span>  
 <span data-ttu-id="07521-106">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="07521-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="07521-107">Необходимо иметь установленную программу Outlook 2010 или более позднюю версию.</span><span class="sxs-lookup"><span data-stu-id="07521-107">You must have Outlook 2010 or later installed.</span></span>  
  
-   <span data-ttu-id="07521-108">Необходимо наличие данных, управляемых MDS, на активном листе в Excel.</span><span class="sxs-lookup"><span data-stu-id="07521-108">You must have MDS-managed data in an active worksheet in Excel.</span></span>  
  
### <a name="to-send-a-shortcut-query-file"></a><span data-ttu-id="07521-109">Отправка файла ярлыка запроса</span><span class="sxs-lookup"><span data-stu-id="07521-109">To send a shortcut query file</span></span>  
  
1.  <span data-ttu-id="07521-110">Убедитесь, что данные на листе представлены в формате, который должен использоваться совместно.</span><span class="sxs-lookup"><span data-stu-id="07521-110">Ensure that the data in the worksheet is in the format you want to share.</span></span> <span data-ttu-id="07521-111">Дополнительные сведения о фильтрации данных и переупорядочении столбцов см. в разделе [Фильтрация данных перед Загрузкой &#40;надстройка MDS для Excel&#41;](filter-data-before-exporting-mds-add-in-for-excel.md) и [Переупорядочение столбцов &#40;надстройка MDS для Excel&#41;](reorder-columns-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="07521-111">For more information about filtering data and reordering columns, see [Filter Data before Loading &#40;MDS Add-in for Excel&#41;](filter-data-before-exporting-mds-add-in-for-excel.md) and [Reorder Columns &#40;MDS Add-in for Excel&#41;](reorder-columns-mds-add-in-for-excel.md).</span></span>  
  
2.  <span data-ttu-id="07521-112">В группе **Сохранение и отправка** нажмите **Отправить запрос**.</span><span class="sxs-lookup"><span data-stu-id="07521-112">In the **Save and Send** group, click **Send Query**.</span></span> <span data-ttu-id="07521-113">Открывается сообщение электронной почты с файлом ярлыка запроса во вложении.</span><span class="sxs-lookup"><span data-stu-id="07521-113">An email message opens and the shortcut query file is attached.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="07521-114">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="07521-114">Next Steps</span></span>  
  
-   <span data-ttu-id="07521-115">Чтобы открыть файл ярлыка запроса, получатель электронного письма должен иметь установленный MDS [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="07521-115">To open the shortcut query file, the recipient of the email must have the MDS [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] installed.</span></span> <span data-ttu-id="07521-116">Получатель должен дважды щелкнуть файл, чтобы открыть его.</span><span class="sxs-lookup"><span data-stu-id="07521-116">The recipient can double-click the file to open it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07521-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="07521-117">See Also</span></span>  
 [<span data-ttu-id="07521-118">Файлы ярлыков запросов (надстройка MDS для Excel)</span><span class="sxs-lookup"><span data-stu-id="07521-118">Shortcut Query Files &#40;MDS Add-in for Excel&#41;</span></span>](shortcut-query-files-mds-add-in-for-excel.md)  
  
  
