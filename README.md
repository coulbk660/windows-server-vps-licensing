# Windows Server VPS Hosting: Is the Licence Included, How Many RDP Users Do You Get, and What Does Year Two Cost? (A Pricing and Plan Checklist)

Windows Server VPS hosting starts around $3.99 a month for a 1 GB evaluation install and runs past $120 a month for a 16 vCPU machine with 64 GB of RAM. The headline rate explains less than half of that spread. The rest comes down to three things: whether a Windows licence sits inside the monthly fee, how many people need to log in over RDP at once, and whether anyone else is going to patch and monitor the box for you.

Work through those three in order and most of the confusing price gaps disappear. What follows is the arithmetic behind each one, using the numbers providers publish, plus the version and licensing traps that only show up after you have already paid.

> **Quick pick:** if you already own a Windows Server key or an enterprise agreement, SpinServers runs Windows on BYOL terms in San Jose and Dallas, so the monthly fee does not carry a licence you have already bought, and IPMI access is there when an RDP misconfiguration locks you out. For a workload that has outgrown a shared-vCPU slice, that is usually the cheaper structure.
> 👉 [See SpinServers' current Windows server configurations and pricing](https://bit.ly/Spinservers)

## The licence is either bundled, added per core, or yours to bring

Three commercial models sit behind the same product name, and they are not interchangeable.

| Provider | What ships at order | What the licence costs | The catch |
| --- | --- | --- | --- |
| Hostwinds | Windows Server image, activated at deployment | Included in the plan price | Fully managed by default; unmanaged cuts up to 50% off |
| Contabo | Windows Server Standard preinstalled | Included in the plan price | Unmanaged; snapshots and Auto Backup are paid add-ons |
| MassiveGRID | Evaluation build (2016, 2019, 2022, 2025) | $0 for 180 days, then $6.31 per vCPU | Must be activated online within the first 10 days |
| reg.cloud | Windows Server 2022 Evaluation image | Free image for 180 days; BYOL supported | Priced in roubles, regions in Russia |
| SpinServers | Windows install on its servers | BYOL: you supply the key | Confirm the current template list when you order |

Hostwinds and Contabo fold the licence into the plan. MassiveGRID and reg.cloud hand you Microsoft's evaluation build and charge for a licence only if you want one before day 180. SpinServers expects you to arrive with a key. A $15 plan with a bundled licence and a $10 plan without one are not competing on the same terms, so comparing them line by line is wasted effort until you know which column you are in.

## What the 180-day evaluation actually means

MassiveGRID spells out the mechanics more clearly than most: the evaluation build must be activated online within the first 10 days, then runs with full features for 180 days, with the remaining days displayed on the desktop. After day 180 the server keeps your data and installed software but shuts down every hour and accepts only security updates until a licence is added. Adding that licence converts the installation in place, with no reinstall and no migration.

The licence itself is $6.31 per vCPU. That is a one-off charge, not a monthly one, which is where a lot of cost comparisons go wrong. Four vCPUs means about $25 once, and the monthly fee is unchanged afterwards. Pay it in month one and the evaluation clock never matters.

reg.cloud runs the same model with a Windows Server 2022 Evaluation image that is free for 180 days; you pay only for CPU, RAM and disk during that window, then either activate or use your own key on the preinstalled image. If you already hold a licence, bring-your-own-key removes the charge entirely.

The evaluation route suits two readers: anyone testing whether an application behaves on Server 2022 or 2025 before committing, and anyone who owns licences already. It does not suit a production box you plan to leave unattended for six months, because the hourly shutdown is not a soft warning.

👉 [Check what a SpinServers Windows server costs when you supply the key](https://bit.ly/Spinservers)

## Two admin sessions, then $8.90 each

Every Windows VPS at MassiveGRID includes two admin sessions. A third concurrent user needs an extra RDP user licence at $8.90 per user per month. Three simultaneous logins means one extra licence; six means four, or $35.60 a month on top of the server, which can exceed the cost of the server itself on entry plans.

That number decides more purchases than RAM does. A two-person accounting setup fits inside the included sessions at no extra cost. A five-person team running Sage or a CRM over RDP is really buying a server plus three user licences, and the second figure should be in the budget from the start. Remote Desktop Services deployments sit outside this entirely and need their own licensing.

Two operational details are worth knowing before you pick a provider. Disconnecting the RDP window does not end the session, so trading terminals, bots and scheduled tasks keep running after you close the client, which is the whole point of running them on a server rather than a desktop. RDP clients exist for Windows, macOS, iOS, Android and Linux. And when a firewall rule or a changed RDP port locks you out, a KVM or VNC console in the control panel gets you back in without a support ticket; IONOS and reg.cloud both provide one, and reg.cloud connects over the default port 3389 with the administrator password sent by email at creation.

## What year three costs after the promotional rate ends

Contabo publishes two prices side by side. CLOUD VPS 12 with Windows Server is listed at $93.60 a month, with $87.60 shown for the first 24 months. CLOUD VPS 16 is $120.10, or $111.20 for the same period. The 18-core plan is quoted in euros, €49.00 with €39.20 for the first 24 months, so keep it out of any dollar total you build.

The gap is small on those plans, roughly 6 to 7 percent, and it expires after two years. Budget the list price from year three and the renewal never arrives as a surprise. Hostwinds takes a different route to the same place: unmanaged service costs up to 50% less than managed, so the discount reflects work you take on rather than a temporary promotion.

Watch the currency and the term on every quote. reg.cloud bills in roubles and shows a monthly and an hourly rate for each plan, for example 560.57 ₽ a month or 0.77 ₽ an hour for 1 vCPU, 1 GB of RAM and 10 GB of NVMe. Hourly billing is useful for a two-day migration test and expensive for anything permanent.

## Managed, self-managed, or support with a scope

"Managed" is the least standardised word in this market.

Hostwinds is genuinely fully managed, with nightly backups built on Windows Shadow Copy, monitoring that opens tickets automatically, instant plan upgrades, an external cloud firewall that sits outside Windows' own firewall, and one-click volume attachment. Hostwinds does not sell MSSQL licences; you buy those from Microsoft and its technicians will help install them. Backups cost $1 a month plus $0.03 per GB. Plesk or SolidCP can be added, Chrome comes preinstalled, and Windows Update is not forced, though leaving it on is the sensible default.

MassiveGRID's Windows VPS and Windows Dedicated VPS are self-managed with 24/7 infrastructure support. Full management, including OS patching, backups and monitoring, exists only on its Managed Cloud Dedicated Server line, which includes Windows Server Standard and an optional SQL Server Web licence. SQL Server Express is free on the cheaper tiers; Web and Standard require your own licence.

Contabo describes its Windows VPS as unmanaged, with snapshots or Auto Backup available as add-ons. IONOS provides free support within a published scope, which covers infrastructure rather than your application configuration. None of this is a flaw, but a $29 plan that leaves patching to you is not cheaper than a $45 plan that does not, once you count the hours.

## Where SpinServers fits in this picture

SpinServers runs its own hardware in San Jose, California and Dallas, Texas, on a privately owned Tier III datacenter with 2N power from separate substations and a multihomed, DDoS-protected network. Ports go up to 2×40 Gbps on its unmetered line, each server includes one IPv4 and an IPv6 /64, free IP block announcement, a free VPC, and firewalled IPMI/iKVM access. Windows, Linux and ESXi install automatically from the client portal, and the facility is SOC 2 certified with HIPAA and PCI compliance listed.

The licensing model is the part that matters for this comparison. SpinServers documents its Windows servers as BYOL: you bring the key, and you are not paying the provider a monthly licence fee. For anyone holding Windows Server licences through an enterprise agreement, that removes the largest recurring line item in the quote. The company's published OS list comes from an older post that names Server 2016 and 2019, so confirm that the 2022 or 2025 template you need is available at order rather than assuming it.

This is not the cheapest way to get a 1 GB Windows box, and it is not meant to be. It makes sense at the point where a shared-vCPU plan runs out of headroom, or where a licence you already own is being billed back to you every month by somebody else.

👉 [Compare SpinServers' Windows server options in San Jose and Dallas](https://bit.ly/Spinservers)

## Server 2025, Windows 11 Pro, or Linux

Windows Server 2025 is the default on new deployments. Server 2016, 2019 and 2022 remain available for software that has not been certified on the newer release, and 2025 adds hotpatching without reboots, Credential Guard, accelerated networking and NVMe optimisation. Choosing 2016 for a new project buys nothing.

Windows 11 Pro is a different product with different rules. Desktop editions allow a single interactive session, and Microsoft does not let hosting providers rent them, so you install unactivated and enter your own key after first login. Minimum RAM is 2 GB, which puts the smallest configuration at 1 vCPU, 2 GB and 32 GB of NVMe for $4.79 a month at MassiveGRID, against $3.99 for the 1 GB Windows Server Starter. Windows 10 Pro reached end of support on 14 October 2025 and no longer receives security updates, so it should not appear in a new build.

Linux costs nothing in licences and carries a smaller attack surface, which is why it underpins the LAMP stack most web applications still run on. If there is no Windows-only application in the plan, the Windows premium buys you nothing.

One trap worth flagging: at IONOS, choosing Windows means you cannot switch that server to Linux later. You would place a new order. If keeping the option to change operating systems matters, its Cloud Server line preserves it.

## Matching the plan to the job

Shared vCPU is enough for a remote desktop for one or two people, a small IIS site, bots, or desktop accounting software. That is exactly the workload MassiveGRID's $3.99 Windows VPS tier targets.

Reserved cores and memory start to matter with SQL Server, IIS under real load, three or more simultaneous RDP users, or emulator and SEO farms running many instances. MassiveGRID's Windows Dedicated VPS starts at $18.84 a month for that reason, and the price difference against the shared tier is smaller than the cost of diagnosing a query that starves because another tenant is busy.

GPU work, including CUDA, rendering and model training, needs a GPU tier rather than more vCPU. reg.cloud lists one alongside its standard plans. For a short-lived environment, a test bench or a release check, hourly billing removes the month-long commitment entirely.

## Questions that come up before ordering

**Can I upgrade the plan later?** Hostwinds offers instant upgrades in its control panel. Contabo lets you change CPU, RAM and storage on demand, and reg.cloud supports both scaling up and scaling down.

**What do backups cost?** Hostwinds charges $1 a month plus $0.03 per GB for incremental backups. Contabo sells Auto Backup as an add-on alongside snapshots. reg.cloud includes daily automatic saves.

**What about SQL Server licensing?** Hostwinds does not resell MSSQL licences, so you buy from Microsoft and install it yourself. MassiveGRID gives you SQL Server Express free and expects you to bring a licence for Web or Standard.

**Should Windows Update stay on?** Hostwinds does not force it and lets you disable it, though enabling it is the safer choice. Contabo's own setup guidance is to run Windows Update and reboot when prompted, restrict RDP to trusted IPs or a VPN, and remove unused roles.

## How to decide

If two people or fewer will log in and the workload is light, take the cheapest plan whose licence position you understand, and check whether the licence is bundled before comparing the monthly rate.

If three or more people need simultaneous RDP access, add $8.90 per extra user per month to every quote, then compare. Plans that looked 30% apart often land within a few dollars of each other once the user count is in.

If you already own Windows Server licences, or the workload has outgrown shared vCPU, a BYOL provider removes both the licence markup and the noisy-neighbour problem.

Before you pay, confirm two things in writing: whether the Windows licence is included, and how many concurrent sessions you get. Those two answers change the real monthly cost more than any CPU benchmark.

👉 [Start with SpinServers' current Windows server listings](https://bit.ly/Spinservers)
