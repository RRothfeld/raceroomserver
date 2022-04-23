# Raceroom "Rasern" Server
## Server settings
- Google Compute Engine
- 2 vCPUs, 2 Gb RAM, Windows Server
- Set network tag: rrre (allows ingress and egress for TCP:60001,60004,8088 and UDP:60000,60002,60003,60005)

## First time VM setup

- Execute: `Dism /online /enable-feature /featurename:Server-Gui-Mgmt /featurename:Server-Gui-Shell /featurename:ServerCore-FullServer /all`
- Add to crontab: `@reboot git -C ./raceroomserver pull && ( cd raceroomserver && exec wine RRRE_Dedicated.exe )`