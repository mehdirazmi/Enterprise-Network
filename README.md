# EnterpriseNet — Enterprise Network Infrastructure Lab
![Network Topology](<docs/Topology.png>)
A hands-on enterprise networking project built with Cisco routers and switches in **PNETLab**.

EnterpriseNet focuses on network segmentation, routing, network services, access control, security, and infrastructure management in a simulated enterprise environment.

> **Project Status:** Configuration and documentation are in progress. Final end-to-end validation is pending.

---

## Table of Contents

- [English Documentation](#english-documentation)
- [Project Objectives](#project-objectives)
- [Network Topology](#network-topology)
- [VLAN and IP Addressing Plan](#vlan-and-ip-addressing-plan)
- [Technologies and Features](#technologies-and-features)
- [NAT/PAT](#natpat)
- [Repository Structure](#repository-structure)
- [Testing and Validation](#testing-and-validation)
- [Learning Outcomes](#learning-outcomes)
- [Persian Documentation](#مستندات-فارسی)
- [Author](#author)

---

# English Documentation

## Project Objectives

The main objectives of EnterpriseNet are to:

- Design a structured enterprise network using multiple VLANs.
- Configure inter-VLAN routing and IP addressing.
- Provide DHCP services for client networks.
- Implement dynamic routing between routers using OSPF.
- Apply access control policies using ACLs.
- Configure Layer 2 security features on access switches.
- Enable secure remote device management through SSH.
- Configure NAT/PAT for intended outbound connectivity.
- Document the network topology, configurations, and test results.

## Network Topology

The lab consists of two routers, two switches, multiple departmental VLANs, and a dedicated server network.

### Network Devices

- **R1:** Provides routing for VLANs 10, 20, and 30, participates in OSPF, and has NAT/PAT configured.
- **R2:** Provides connectivity for the Management and Server networks and participates in OSPF.
- **SW1 and SW2:** Provide VLAN segmentation, 802.1Q trunking, and Layer 2 security.
- **Cloud/NAT:** Provides the intended upstream connectivity path for outbound traffic.

### Topology Diagram

The topology diagram will be stored in `docs/topology.png`.



## VLAN and IP Addressing Plan

| VLAN ID | Name         | Network           | Default Gateway |
| ------: | ------------ | ----------------- | --------------- |
|      10 | IT           | `192.168.10.0/24` | `192.168.10.1`  |
|      20 | HR           | `192.168.20.0/24` | `192.168.20.1`  |
|      30 | Finance      | `192.168.30.0/24` | `192.168.30.1`  |
|      40 | Management   | `192.168.40.0/24` | `192.168.40.1`  |
|      50 | Servers      | `192.168.50.0/24` | `192.168.50.1`  |
|     999 | UNUSED_PORTS | Not applicable    | Not applicable  |

Each VLAN represents a separate logical network. VLAN 999 is reserved for unused switch ports.

## Technologies and Features

### Routing and Network Services

- VLAN segmentation
- Inter-VLAN routing
- DHCP configuration
- OSPF dynamic routing
- NAT/PAT configuration

### Switching and Layer 2 Security

- IEEE 802.1Q trunking
- Access port VLAN assignment
- Allowed-VLAN filtering
- PortFast
- BPDU Guard
- Switch port security
- Unused-port isolation

### Security and Management

- Access Control Lists (ACLs)
- SSH remote management
- VLAN-based network separation
- Management network design

## NAT/PAT

NAT/PAT is configured on R1 to support outbound connectivity for internal networks.

- NAT inside and outside roles are configured on R1.
- Dynamic PAT is intended to translate internal addresses for outbound traffic.
- Connectivity through the PNETLab Cloud/NAT interface is pending final validation.

> **Note:** NAT/PAT configuration does not guarantee successful Internet connectivity. Its operation will be considered verified only after testing.

## Repository Structure

The following structure is planned for organizing the project files.

```text
EnterpriseNet/
├── README.md
├── topology/
│   └── EnterpriseNet.unl
├── configs/
│   ├── R1.cfg
│   ├── R2.cfg
│   ├── SW1.cfg
│   └── SW2.cfg
├── docs/
│   └── topology.png

```

*Update this structure to match the actual files exported from PNETLab. Do not include placeholder files that do not exist.*

## Testing and Validation

The final validation phase will cover the following items:

- [ ] VLAN membership and trunk configuration
- [ ] DHCP address assignment
- [ ] Inter-VLAN connectivity
- [ ] OSPF neighbor adjacency and route learning
- [ ] ACL policy enforcement
- [ ] SSH access to network devices
- [ ] Port Security and BPDU Guard behavior
- [ ] NAT/PAT translation and outbound connectivity
- [ ] End-to-end connectivity between permitted networks

Test results and relevant command outputs will be documented after validation.

## Learning Outcomes

This project provides practical experience with:

- Cisco IOS configuration
- IP addressing and subnetting
- VLANs and trunking
- Dynamic routing with OSPF
- DHCP and network services
- Access control and Layer 2 security
- Network troubleshooting and documentation

## Disclaimer

EnterpriseNet is an educational lab designed for practical networking exercises. Features should be considered operational only after their configuration and behavior have been validated.

---

# مستندات فارسی

## معرفی پروژه

**EnterpriseNet** یک پروژه عملی شبکه سازمانی است که با استفاده از روترها و سوئیچ‌های سیسکو در محیط **PNETLab** طراحی و پیکربندی می‌شود.

تمرکز این پروژه بر تفکیک شبکه، مسیریابی، سرویس‌های شبکه، کنترل دسترسی، امنیت و مدیریت زیرساخت در یک محیط شبیه‌سازی‌شده سازمانی است.

> **وضعیت پروژه:** پیکربندی و مستندسازی در حال تکمیل است. تست نهایی ارتباطات و عملکرد سرتاسری شبکه هنوز انجام نشده است.

## اهداف پروژه

اهداف اصلی این پروژه عبارت‌اند از:

- طراحی شبکه سازمانی ساختاریافته با استفاده از چند VLAN
- پیکربندی مسیریابی بین VLANها و آدرس‌دهی IP
- ارائه سرویس DHCP به شبکه‌های کاربران
- پیاده‌سازی مسیریابی پویا بین روترها با استفاده از OSPF
- اعمال سیاست‌های کنترل دسترسی با استفاده از ACL
- پیکربندی قابلیت‌های امنیتی لایه دوم روی سوئیچ‌ها
- فراهم‌کردن مدیریت امن تجهیزات از طریق SSH
- پیکربندی NAT/PAT برای ارتباطات خروجی موردنظر
- مستندسازی توپولوژی، تنظیمات و نتایج تست‌ها

## توپولوژی شبکه

این آزمایشگاه از دو روتر، دو سوئیچ، چند VLAN سازمانی و یک شبکه مجزا برای سرورها تشکیل شده است.

### تجهیزات شبکه

- **R1:** مسیریابی VLANهای 10، 20 و 30، شرکت در فرایند OSPF و پیکربندی NAT/PAT
- **R2:** برقراری ارتباط با شبکه‌های مدیریت و سرورها و شرکت در فرایند OSPF
- **SW1 و SW2:** تفکیک شبکه با VLAN، ایجاد لینک‌های Trunk مبتنی بر 802.1Q و اعمال تنظیمات امنیتی لایه دوم
- **Cloud/NAT:** مسیر در نظر گرفته‌شده برای ارتباطات خروجی شبکه

### تصویر توپولوژی

تصویر توپولوژی در مسیر `docs/topology.png` قرار خواهد گرفت.



## طرح VLAN و آدرس‌دهی IP

| شناسه VLAN | نام          | شبکه              | دروازه پیش‌فرض |
| ---------: | ------------ | ----------------- | -------------- |
|         10 | IT           | `192.168.10.0/24` | `192.168.10.1` |
|         20 | HR           | `192.168.20.0/24` | `192.168.20.1` |
|         30 | Finance      | `192.168.30.0/24` | `192.168.30.1` |
|         40 | Management   | `192.168.40.0/24` | `192.168.40.1` |
|         50 | Servers      | `192.168.50.0/24` | `192.168.50.1` |
|        999 | UNUSED_PORTS | ندارد             | ندارد          |

هر VLAN نمایانگر یک شبکه منطقی مجزا است. VLAN 999 برای پورت‌های بلااستفاده سوئیچ در نظر گرفته شده است.

## فناوری‌ها و قابلیت‌ها

### مسیریابی و سرویس‌های شبکه

- تفکیک شبکه با VLAN
- مسیریابی بین VLANها
- پیکربندی DHCP
- مسیریابی پویا با OSPF
- پیکربندی NAT/PAT

### سوئیچینگ و امنیت لایه دوم

- Trunking مبتنی بر IEEE 802.1Q
- تخصیص VLAN به پورت‌های Access
- محدودکردن VLANهای مجاز روی Trunk
- PortFast
- BPDU Guard
- Port Security
- جداسازی پورت‌های بلااستفاده

### امنیت و مدیریت

- کنترل دسترسی با ACL
- مدیریت از راه دور با SSH
- جداسازی منطقی شبکه‌ها بر اساس VLAN
- طراحی شبکه مدیریت تجهیزات

## NAT/PAT

NAT/PAT روی روتر R1 پیکربندی شده است تا امکان ارتباط خروجی شبکه‌های داخلی فراهم شود.

- نقش‌های NAT Inside و NAT Outside روی R1 تعریف شده‌اند.
- هدف از Dynamic PAT، ترجمه آدرس‌های داخلی برای ترافیک خروجی است.
- عملکرد ارتباط از طریق رابط Cloud/NAT در PNETLab هنوز به‌صورت نهایی تأیید نشده است.

> **نکته:** پیکربندی NAT/PAT به‌تنهایی به معنای برقراری موفق اینترنت نیست. عملکرد آن تنها پس از انجام تست تأیید خواهد شد.

## ساختار مخزن پروژه

ساختار پیشنهادی برای سازمان‌دهی فایل‌های پروژه به شکل زیر است:

```text
EnterpriseNet/
├── README.md
├── topology/
│   └── EnterpriseNet.unl
├── configs/
│   ├── R1.cfg
│   ├── R2.cfg
│   ├── SW1.cfg
│   └── SW2.cfg
├── docs/
│   └── topology.png

```

این ساختار باید با فایل‌هایی که واقعاً از PNETLab خروجی گرفته و در مخزن قرار می‌دهی، تطبیق داده شود.

## تست و اعتبارسنجی

در مرحله تست نهایی، موارد زیر بررسی خواهند شد:

- [ ] عضویت پورت‌ها در VLANها و صحت تنظیمات Trunk
- [ ] تخصیص آدرس IP از طریق DHCP
- [ ] ارتباط بین VLANها
- [ ] وضعیت همسایگی OSPF و یادگیری مسیرها
- [ ] عملکرد قوانین ACL
- [ ] دسترسی SSH به تجهیزات شبکه
- [ ] عملکرد Port Security و BPDU Guard
- [ ] ترجمه آدرس‌ها توسط NAT/PAT و ارتباطات خروجی
- [ ] ارتباط انتهابه‌انتهای شبکه‌های مجاز

نتایج تست‌ها و خروجی‌های مرتبط با دستورات شبکه پس از تکمیل اعتبارسنجی به مستندات اضافه خواهند شد.

## دستاوردهای آموزشی

این پروژه تجربه عملی در زمینه‌های زیر فراهم می‌کند:

- پیکربندی تجهیزات مبتنی بر Cisco IOS
- آدرس‌دهی IP و Subnetting
- VLAN و Trunking
- مسیریابی پویا با OSPF
- DHCP و سرویس‌های شبکه
- کنترل دسترسی و امنیت لایه دوم
- عیب‌یابی و مستندسازی شبکه

## توضیحات تکمیلی

EnterpriseNet یک آزمایشگاه آموزشی برای تمرین عملی مفاهیم شبکه است. قابلیت‌های پروژه تنها پس از بررسی تنظیمات و تأیید عملکرد آن‌ها از طریق تست، عملیاتی و تأییدشده محسوب می‌شوند.

---

## Author | سازنده پروژه

**Mohammad Mehdi Razmi**

- GitHub:[MehdiRazmi](https://github.com/mehdirazmi)
- Project: EnterpriseNet
