---
title: Добавление гиперссылки на URL-адрес (построитель отчетов и службы SSRS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d3392c0b-7b62-4d27-bc04-2bd0c5487d08
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d3db3fc75feca1393e73e698f44db633f09e8dc1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730186"
---
# <a name="add-a-hyperlink-to-a-url-report-builder-and-ssrs"></a><span data-ttu-id="74db1-102">Добавление гиперссылки на URL-адрес (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="74db1-102">Add a Hyperlink to a URL (Report Builder and SSRS)</span></span>
  <span data-ttu-id="74db1-103">Можно добавить к элементу отчета гиперссылку, при щелчке которой будет осуществлен переход в браузере по заданному URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="74db1-103">You can add a hyperlink to a report item when you want your users to be able to click a link in a report and open a browser to the URL that you specify.</span></span> <span data-ttu-id="74db1-104">Гиперссылкой может служить статический URL-адрес или выражение, результатом вычисления которого будет такой адрес.</span><span class="sxs-lookup"><span data-stu-id="74db1-104">A hyperlink can be a static URL or an expression that evaluates to a URL.</span></span> <span data-ttu-id="74db1-105">Если в базе данных есть поле, содержащее URL-адрес, выражение может содержать это поле, что приведет к формированию в отчете динамического списка гиперссылок.</span><span class="sxs-lookup"><span data-stu-id="74db1-105">If you have a field in a database that contains URLs, the expression can contain that field, resulting in a dynamic list of hyperlinks in the report.</span></span> <span data-ttu-id="74db1-106">Гиперссылки можно добавлять в текстовые поля, диаграммы, изображения и датчики.</span><span class="sxs-lookup"><span data-stu-id="74db1-106">You can add hyperlinks to text boxes, images, charts, and gauges.</span></span> <span data-ttu-id="74db1-107">У пользователя должно быть право доступа к указанному URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="74db1-107">You must ensure that the user has access to the URL that you provide.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
 <span data-ttu-id="74db1-108">Можно также задавать URL-адреса отчетов на любом сервере отчетов, на котором имеется разрешение на чтение с помощью URL-запросов к серверу отчетов.</span><span class="sxs-lookup"><span data-stu-id="74db1-108">You can also specify URLs to reports on any report server that you and your users have permission to view using URL requests to the report server.</span></span> <span data-ttu-id="74db1-109">Например, можно указать отчет и скрыть схему документа, когда пользователь впервые просматривает этот отчет.</span><span class="sxs-lookup"><span data-stu-id="74db1-109">For example, you can specify a report and hide the document map for the user when they first view the report.</span></span> <span data-ttu-id="74db1-110">Дополнительные сведения см. в разделе [Доступ по URL-адресу (SSRS)](../url-access-ssrs.md)[документации по службам Reporting Services](https://go.microsoft.com/fwlink/?linkid=121312), входящей в состав электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="74db1-110">For more information, see [URL Access &#40;SSRS&#41;](../url-access-ssrs.md) in the [Reporting Services documentation](https://go.microsoft.com/fwlink/?linkid=121312) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="74db1-111">Гиперссылку на URL-адрес можно добавить к любому элементу, у которого есть свойство **Действие** , — текстовому полю, изображению или вычисляемому ряду в диаграмме.</span><span class="sxs-lookup"><span data-stu-id="74db1-111">You can add a hyperlink to a URL to any item that has an **Action** property, for example, a text box, an image, or a calculated series in a chart.</span></span> <span data-ttu-id="74db1-112">Когда пользователь щелкает этот элемент отчета, выполняется действие, которое было определено.</span><span class="sxs-lookup"><span data-stu-id="74db1-112">When the user clicks that report item, the action that you define takes place.</span></span> <span data-ttu-id="74db1-113">Дополнительные сведения см. в разделах [Диалоговое окно "Свойства действия" (построитель отчетов и службы SSRS)](../action-properties-dialog-box-report-builder-and-ssrs.md) и [Указание путей к внешним элементам (построитель отчетов и службы SSRS)](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="74db1-113">For more information, see the [Action Properties Dialog Box &#40;Report Builder and SSRS&#41;](../action-properties-dialog-box-report-builder-and-ssrs.md) and [Specifying Paths to External Items &#40;Report Builder and SSRS&#41;](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="74db1-114">Чтобы быстро приступить к работе, см. раздел [Учебник. Форматирование текста (построитель отчета)](../tutorial-format-text-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="74db1-114">To quickly get started, see [Tutorial: Format Text &#40;Report Builder&#41;](../tutorial-format-text-report-builder.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="74db1-115">Ссылки, привязанные к полям набора данных, могут стать мишенью для злонамеренного вторжения.</span><span class="sxs-lookup"><span data-stu-id="74db1-115">Links that are bound to dataset fields can be vulnerable to tampering for malicious purposes.</span></span> <span data-ttu-id="74db1-116">Дополнительные сведения см. в разделе [Защищенные отчеты и ресурсы](../security/secure-reports-and-resources.md)[электронной документации](https://go.microsoft.com/fwlink/?LinkId=154888) по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на сайте msdn.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="74db1-116">For more information, see [Secure Reports and Resources](../security/secure-reports-and-resources.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][Books Online](https://go.microsoft.com/fwlink/?LinkId=154888) on msdn.microsoft.com.</span></span>  
  
### <a name="to-add-a-hyperlink"></a><span data-ttu-id="74db1-117">Добавление гиперссылки</span><span class="sxs-lookup"><span data-stu-id="74db1-117">To add a hyperlink</span></span>  
  
1.  <span data-ttu-id="74db1-118">В режиме конструктора щелкните правой кнопкой мыши текстовое поле, рисунок или диаграмму, к которым нужно добавить ссылку, и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="74db1-118">In report design view, right-click the text box, image, or chart to which you want to add a link and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="74db1-119">В диалоговом окне «Свойства» нажмите кнопку **Действие**.</span><span class="sxs-lookup"><span data-stu-id="74db1-119">In the Properties dialog box, click **Action**.</span></span>  
  
3.  <span data-ttu-id="74db1-120">Выберите **Перейти по URL-адресу**.</span><span class="sxs-lookup"><span data-stu-id="74db1-120">Select **Go to URL**.</span></span> <span data-ttu-id="74db1-121">В диалоговом окне появится дополнительная область для этого параметра.</span><span class="sxs-lookup"><span data-stu-id="74db1-121">An additional section appears in the dialog box for this option.</span></span>  
  
4.  <span data-ttu-id="74db1-122">В поле **Выбор URL-адреса**введите или выберите URL-адрес или выражение, результатом которого является URL-адрес, или нажмите стрелку вниз и щелкните имя содержащего URL-адрес поля.</span><span class="sxs-lookup"><span data-stu-id="74db1-122">In **Select URL**, type or select a URL or an expression that evaluates to a URL, or click the drop-down arrow and click the name of a field that contains a URL.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="74db1-123">Автоматическое форматирование текста как ссылки не производится (необязательно).</span><span class="sxs-lookup"><span data-stu-id="74db1-123">(Optional) The text is not automatically formatted as a link.</span></span> <span data-ttu-id="74db1-124">Если ссылка установлена в тексте, будет полезно изменить цвет и стиль текста, чтобы показать, что текст является ссылкой.</span><span class="sxs-lookup"><span data-stu-id="74db1-124">For text, it is helpful to change the color and effect of the text to indicate that the text is a link.</span></span> <span data-ttu-id="74db1-125">Например, измените цвет на синий, а эффект на подчеркивание в разделе **Шрифт** на вкладке «Главная» ленты.</span><span class="sxs-lookup"><span data-stu-id="74db1-125">For example, change the color to blue and the effect to underline in the **Font** section in the Home tab of the Ribbon.</span></span>  
  
7.  <span data-ttu-id="74db1-126">Для проверки ссылки нажмите кнопку **Выполнить** , чтобы выполнить предварительный просмотр отчета, а затем щелкните элемент отчета, для которого была создана ссылка.</span><span class="sxs-lookup"><span data-stu-id="74db1-126">To test the link, click **Run** to preview the report, and then click the report item that you set this link on.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74db1-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="74db1-127">See Also</span></span>  
 <span data-ttu-id="74db1-128">[Интерактивная сортировка, схемы документов и ссылки &#40;построитель отчетов и SSRS&#41;](interactive-sort-document-maps-and-links-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="74db1-128">[Interactive Sort, Document Maps, and Links &#40;Report Builder and SSRS&#41;](interactive-sort-document-maps-and-links-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="74db1-129">Создание схемы документа (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="74db1-129">Create a Document Map &#40;Report Builder and SSRS&#41;</span></span>](create-a-document-map-report-builder-and-ssrs.md)  
  
  
