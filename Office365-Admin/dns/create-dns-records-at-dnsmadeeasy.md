---
title: "Create DNS records at DNSMadeEasy for Office 365"
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_DNSMadeEasy'
- 'O365M_DOM_DNSMadeEasy'
- 'O365E_DOM_DNSMadeEasy'
ms.service: o365-administration
localization_priority: Normal
ms.collection: 
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: e158b079-b054-4b7e-8e01-e55169ce18d7
description: "Learn to verify your domain and set up DNS records for email, Skype for Business Online, and other services at DNSMadeEasy for Office 365."
---

# Create DNS records at DNSMadeEasy for Office 365

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
If DNSMadeEasy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.
  
After you add these records at DNSMadeEasy, your domain will be set up to work with Office 365 services.
  
To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  
## Add a TXT record for verification
<a name="BKMK_verify"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
> [!IMPORTANT]
> For DNSMadeEasy accounts, the domain you added was purchased from a separate domain registrar. DNSMadeEasy does not offer domain registration services. Your ability to log in at DNSMadeEasy and create the DNS record is sufficient proof of ownership. 
  
1. To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.
    
2. On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update. 
    
3. On the **Managed DNS** page, in the **TXT Records** area, select the ( **+**) control ( **Add new**).
    
    (You may have to scroll down.)
    
4. In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    ||||
    |:-----|:-----|:-----|
    |**Name** <br/> |**Value** <br/> |**TTL** <br/> |
    |(Leave this field empty.)  <br/> |MS=ms *XXXXXXXX*  <br/> **Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365. [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |1800  <br/> |
   
5. Select **Submit**.
    
6. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.

    
2. On the **Domains** page, select the domain that you are verifying. 
    
3. On the **Setup** page, select **Start setup**.
    
4. On the **Verify domain** page, select **Verify**.
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  
## Add an MX record so email for your domain will come to Office 365
<a name="BKMK_add_MX"> </a>

1. To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.
    
2. On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update. 
    
    On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update. 
    
    ![DNSMadeEasy-BP-Configure-1-2](../media/8d8f403e-d7cd-429e-913b-dacb1f4644a2.png)
  
3. On the **Managed DNS** page, in the **MX Records** area, select the **(+)** control ( **Add new**).
    
    (You may have to scroll down.)
    
    ![DNSMadeEasy-BP-Configure-2-1](../media/404c73bf-1db4-4d68-82d8-68303f418ed4.png)
  
4. In the **Add MX Records** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (You may have to scroll down.)
    
    |**Name**|**Server**|**MX Level**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> **This value MUST end with a period (.)** <br/> **Note:** Get your \<*domain-key*\> from your Office 365 account. [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |10  <br/> For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> |1800  <br/> |
   
    ![DNSMadeEasy-BP-Configure-2-2](../media/69b53af9-1eec-435c-8434-1b6058c1ec82.png)
  
5. Select **Submit**.
    
    ![DNSMadeEasy-BP-Configure-2-3](../media/381054a6-bb85-4ebb-b576-42cbba78ed1b.png)
  
6. If there are any other MX records listed in the **MX Records** section, delete all of them by selecting each one. 
    
    ![DNSMadeEasy-BP-Configure-2-4-1](../media/58a07769-0b30-4111-b555-bfc3b82a7d4c.png)
  
7. When all records are selected, select **Delete selected**.
    
    ![DNSMadeEasy-BP-Configure-2-4-2](../media/e9064c07-1ce7-4387-b47a-90d4193da374.png)
  
8. In the **Delete MX Records** dialog box, select **Delete** to confirm your changes. 
    
    ![DNSMadeEasy-BP-Configure-2-5](../media/03c405e5-868f-468f-b6d2-046d27b201fb.png)
  
## Add the six CNAME records that are required for Office 365
<a name="BKMK_add_CNAME"> </a>

1. To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.
    
2. On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update. 
    
3. On the **Managed DNS** page, in the **CNAME Records** area, select the **(+)** control ( **Add new**).
    
    (You may have to scroll down.)
    
    ![DNSMadeEasy-BP-Configure-3-1](../media/a5feb238-690d-4b64-a625-91a82b3f4068.png)
  
4. Add the first of the six CNAME records.
    
    In the **Add CNAME Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table. 
    
    |**Name**|**Alias to**|**TTL**|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com.  <br/> **This value MUST end with a period (.)** <br/> |1800  <br/> |
    |sip  <br/> |sipdir.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |1800  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |1800  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net.  <br/> **This value MUST end with a period (.)** <br/> |1800  <br/> |
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **This value MUST end with a period (.)** <br/> |1800  <br/> |
   
    ![DNSMadeEasy-BP-Configure-3-2](../media/de6dddcd-bf0a-4993-ab4c-a6d10167bf34.png)
  
5. Select **Submit**.
    
    ![DNSMadeEasy-BP-Configure-3-3](../media/e44ef73e-99cb-41ce-a3f2-549cb2f29eef.png)
  
6. Add each of the other five CNAME records.
    
    In the **CNAME Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record. 
    
    Repeat this process until you have created all six CNAME records.
    
## Add a TXT record for SPF to help prevent email spam
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values. Need examples? Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0). To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md). 
  
1. To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.
    
2. On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update. 
    
3. On the **Managed DNS** page, in the **TXT Records** area, select the **(+)** control ( **Add new**).
    
    (You may have to scroll down.)
    
    ![DNSMadeEasy-BP-Configure-4-1](../media/657b87a5-dcb4-4ae7-8f27-bd857f0f4189.png)
  
4. In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    |**Name**|**Value**|**TTL**|
    |:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.           |1800  <br/> |
   
    ![DNSMadeEasy-BP-Configure-4-2](../media/b317bcb9-18c6-4609-a8f4-963823032669.png)
  
5. Select **Submit**.
    
    ![DNSMadeEasy-BP-Configure-4-3](../media/8a1c53c3-1222-4127-a190-70f6f5059433.png)
  
## Add the two SRV records that are required for Office 365
<a name="BKMK_add_SRV"> </a>

1. To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.
    
2. On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update. 
    
3. On the **Managed DNS** page, in the **SRV Records** area, select the **(+)** control ( **Add new**).
    
    (You may have to scroll down)
    
    ![DNSMadeEasy-BP-Configure-5-1](../media/5c9e8f50-adbd-4f23-8ce3-2844b2896f3f.png)
  
4. Add the first of the two SRV records.
    
    In the **Add SRV Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table. 
    
    |**Name**|**Priority**|**Weight**|**Port**|**Host**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip._tls  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |1800  <br/> |
    |_sipfederationtls._tcp  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |1800  <br/> |
   
    ![DNSMadeEasy-BP-Configure-5-2](../media/e1155f94-575f-441a-9a61-d948391d42ca.png)
  
5. Select **Submit**.
    
    ![DNSMadeEasy-BP-Configure-5-3](../media/7eae54e1-08bd-4902-afdf-fd5cc251ab59.png)
  
6. Add the other SRV record.
    
    In the **SRV Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record. 
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  

