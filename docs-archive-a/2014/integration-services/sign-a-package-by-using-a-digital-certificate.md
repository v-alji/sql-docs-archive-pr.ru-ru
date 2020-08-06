---
title: Подписывание пакета с помощью цифрового сертификата | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- digital signatures [Integration Services]
- signing packages [Integration Services]
- signatures [Integration Services]
ms.assetid: 182b115e-0fe2-4717-8dff-183f9eb6e397
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6bd0f73d609623f882e474c96a01cd3bc0274b6b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751256"
---
# <a name="sign-a-package-by-using-a-digital-certificate"></a><span data-ttu-id="37d23-102">Подписание пакета цифровым сертификатом</span><span class="sxs-lookup"><span data-stu-id="37d23-102">Sign a Package by Using a Digital Certificate</span></span>
  <span data-ttu-id="37d23-103">Данный раздел описывает подписание пакета служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] цифровым сертификатом.</span><span class="sxs-lookup"><span data-stu-id="37d23-103">This topic describes how to sign an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package with a digital certificate.</span></span> <span data-ttu-id="37d23-104">Цифровая подпись может использоваться совместно с другими методами предотвращения загрузки и выполнения недействительного пакета.</span><span class="sxs-lookup"><span data-stu-id="37d23-104">You can use a digital signature, together with other settings, to prevent a package that is not valid from loading and running.</span></span>  
  
 <span data-ttu-id="37d23-105">Перед подписанием пакета служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] необходимо выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="37d23-105">Before you can sign an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package, you must do the following tasks:</span></span>  
  
-   <span data-ttu-id="37d23-106">Создайте или получите закрытый ключ для сертификата и сохраните его на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="37d23-106">Create or obtain a private key to associate with the certificate, and store this private key on the local computer.</span></span>  
  
-   <span data-ttu-id="37d23-107">Получите сертификат для цифрового подписывания от доверенной службы сертификации.</span><span class="sxs-lookup"><span data-stu-id="37d23-107">Obtain a certificate for the purpose of code signing from a trusted certification authority.</span></span> <span data-ttu-id="37d23-108">Для получения или создания сертификата можно воспользоваться одним из следующих методов.</span><span class="sxs-lookup"><span data-stu-id="37d23-108">You can use one of the following methods to obtain or create a certificate:</span></span>  
  
    -   <span data-ttu-id="37d23-109">Получите сертификат от публичной, коммерческой службы выдачи сертификатов.</span><span class="sxs-lookup"><span data-stu-id="37d23-109">Obtain a certificate from a public, commercial certification authority that issues certificates.</span></span>  
  
    -   <span data-ttu-id="37d23-110">Получите на сервере сертификации сертификат, позволяющий организации самостоятельно выпускать сертификаты внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="37d23-110">Obtain a certificate from a certificate server, that enables an organization to internally issue certificates.</span></span> <span data-ttu-id="37d23-111">Корневой сертификат, используемый для подписания этого сертификата, необходимо добавить в хранилище **Доверенные корневые центры сертификации** .</span><span class="sxs-lookup"><span data-stu-id="37d23-111">You have to add the root certificate that is used to sign the certificate to the **Trusted Root Certification Authorities** store.</span></span> <span data-ttu-id="37d23-112">Для добавления корневого сертификата можно воспользоваться оснасткой «Сертификаты» в консоли управления [!INCLUDE[msCoName](../includes/msconame-md.md)] MMC.</span><span class="sxs-lookup"><span data-stu-id="37d23-112">To add the root certificate, you can use the Certificates snap-in for the [!INCLUDE[msCoName](../includes/msconame-md.md)] Management Console (MMC).</span></span> <span data-ttu-id="37d23-113">Дополнительные сведения см. в разделе «[Службы сертификатов](https://go.microsoft.com/fwlink/?LinkId=100755)» библиотеки MSDN.</span><span class="sxs-lookup"><span data-stu-id="37d23-113">For more information, see the topic, "[Certificate Services](https://go.microsoft.com/fwlink/?LinkId=100755)," in the MSDN library.</span></span>  
  
    -   <span data-ttu-id="37d23-114">Создайте собственный сертификат только в тестовых целях.</span><span class="sxs-lookup"><span data-stu-id="37d23-114">Create your own certificate for testing purposes only.</span></span> <span data-ttu-id="37d23-115">Средство создания сертификатов (Makecert.exe) порождает сертификаты X.509 для тестовых целей.</span><span class="sxs-lookup"><span data-stu-id="37d23-115">The Certificate Creation Tool (Makecert.exe) generates X.509 certificates for testing purposes.</span></span> <span data-ttu-id="37d23-116">Дополнительные сведения см. в разделе "[Средство создания сертификатов (Makecert.exe)](https://go.microsoft.com/fwlink/?LinkId=100756)" библиотеки MSDN.</span><span class="sxs-lookup"><span data-stu-id="37d23-116">For more information, see the topic, "[Certificate Creation Tool (Makecert.exe)](https://go.microsoft.com/fwlink/?LinkId=100756)," in the MSDN Library.</span></span>  
  
     <span data-ttu-id="37d23-117">Дополнительные сведения о сертификатах см. в электронной документации по оснастке «Сертификаты».</span><span class="sxs-lookup"><span data-stu-id="37d23-117">For more information about certificates, see the online Help for the Certificates snap-in.</span></span> <span data-ttu-id="37d23-118">Дополнительные сведения о подписывании цифровых активов см. в разделе «[Подписывание и проверка кода при помощи технологии Authenticode](https://go.microsoft.com/fwlink/?LinkId=78100)» библиотеки MSDN.</span><span class="sxs-lookup"><span data-stu-id="37d23-118">For more information about how to sign digital assets, see the topic, "[Signing and Checking Code with Authenticode](https://go.microsoft.com/fwlink/?LinkId=78100)," in the MSDN Library.</span></span>  
  
-   <span data-ttu-id="37d23-119">Убедитесь, что сертификат поддерживает подписание кода.</span><span class="sxs-lookup"><span data-stu-id="37d23-119">Make sure that the certificate has been enabled for code signing.</span></span> <span data-ttu-id="37d23-120">Чтобы определить, поддерживает ли сертификат подписание кода, проверьте свойства сертификата в оснастке «Сертификаты».</span><span class="sxs-lookup"><span data-stu-id="37d23-120">To determine whether a certificate is enabled for code signing, review the properties of the certificate in the Certificates snap-in.</span></span>  
  
-   <span data-ttu-id="37d23-121">Сохраните сертификат в персональном хранилище.</span><span class="sxs-lookup"><span data-stu-id="37d23-121">Store the certificate in the Personal store.</span></span>  
  
 <span data-ttu-id="37d23-122">После выполнения описанных выше задач можно подписать пакет, следуя приведенной далее процедуре.</span><span class="sxs-lookup"><span data-stu-id="37d23-122">After you have completed the previous tasks, you can use the following procedure to sign a package.</span></span>  
  
### <a name="to-sign-a-package"></a><span data-ttu-id="37d23-123">Подписывание пакета</span><span class="sxs-lookup"><span data-stu-id="37d23-123">To sign a package</span></span>  
  
1.  <span data-ttu-id="37d23-124">В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , содержащий подписываемый пакет.</span><span class="sxs-lookup"><span data-stu-id="37d23-124">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package to be signed.</span></span>  
  
2.  <span data-ttu-id="37d23-125">Чтобы открыть пакет, дважды щелкните его в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="37d23-125">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="37d23-126">В конструкторе служб [!INCLUDE[ssIS](../includes/ssis-md.md)] или в меню **Службы SSIS** нажмите **Цифровая подпись**.</span><span class="sxs-lookup"><span data-stu-id="37d23-126">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, on the **SSIS** menu, click **Digital Signing**.</span></span>  
  
4.  <span data-ttu-id="37d23-127">В диалоговом окне **Цифровая подпись** нажмите **Подписать**.</span><span class="sxs-lookup"><span data-stu-id="37d23-127">In the **Digital Signing** dialog box, click **Sign**.</span></span>  
  
5.  <span data-ttu-id="37d23-128">Выберите сертификат в диалоговом окне **Выбор сертификата** .</span><span class="sxs-lookup"><span data-stu-id="37d23-128">In the **Select a Certificate** dialog box, select a certificate.</span></span>  
  
6.  <span data-ttu-id="37d23-129">Чтобы просмотреть сведения о сертификате, нажмите кнопку **Просмотреть сертификат**(необязательно).</span><span class="sxs-lookup"><span data-stu-id="37d23-129">(Optional) Click **View Certificat**e to view certificate information.</span></span>  
  
7.  <span data-ttu-id="37d23-130">Нажмите кнопку **ОК** , чтобы закрыть диалоговое окно **Выбор сертификата** .</span><span class="sxs-lookup"><span data-stu-id="37d23-130">Click **OK** to close the **Select a Certificate** dialog box.</span></span>  
  
8.  <span data-ttu-id="37d23-131">Нажмите кнопку **ОК** , чтобы закрыть диалоговое окно **Цифровая подпись** .</span><span class="sxs-lookup"><span data-stu-id="37d23-131">Click **OK** to close the **Digital Signing** dialog box.</span></span>  
  
9. <span data-ttu-id="37d23-132">Чтобы сохранить обновленный пакет, выберите пункт **Сохранить выбранные элементы** в меню **Файл** .</span><span class="sxs-lookup"><span data-stu-id="37d23-132">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
     <span data-ttu-id="37d23-133">Теперь пакет подписан, но службы [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] необходимо настроить для проверки наличия и корректности цифровой подписи перед загрузкой пакета.</span><span class="sxs-lookup"><span data-stu-id="37d23-133">Although the package has been signed, you must now configure [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] to check or verify the digital signature before loading the package.</span></span> <span data-ttu-id="37d23-134">Дополнительные сведения см. в разделе [Определение источника пакетов с помощью цифровых подписей](security/identify-the-source-of-packages-with-digital-signatures.md).</span><span class="sxs-lookup"><span data-stu-id="37d23-134">For more information, see [Identify the Source of Packages with Digital Signatures](security/identify-the-source-of-packages-with-digital-signatures.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37d23-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="37d23-135">See Also</span></span>  
 [<span data-ttu-id="37d23-136">Общие сведения о безопасности (службы Integration Services)</span><span class="sxs-lookup"><span data-stu-id="37d23-136">Security Overview &#40;Integration Services&#41;</span></span>](security/security-overview-integration-services.md)  
  
  
