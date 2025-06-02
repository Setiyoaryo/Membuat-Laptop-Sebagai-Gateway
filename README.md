# Membuat-Laptop-Sebagai-Gateway

### Requirements
1. Zero Tier Account
2. Windows 11/10 Pro
3. NetNat

### Hubungkan Laptop ke Zero Tier Menggunakan Network ID
1. Masuk ke Dashboard Zero Tier
2. Masuk ke menu Advanced
3. Add Route ke Network Lokal dengan Laptop Sebagai Next Hop
4. Save

### Aktifkan IP Forwarding di Powershell
```Bash
Set-ItemProperty -Path HKLM:\SYSTEM\CurrentControlSet\Services\Tcpip\Parameters -Name IPEnableRouter -Value 1
```

### Aktifkan Windows Optional Feature NetNat
```Bash
Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Hyper-V-All -All
```

### Aktifkan NAT ke Network lokal Zero Tier
```Bash
New-NetNat -Name "ZTNAT" -InternalIPInterfaceAddressPrefix a.b.c.d/24
```
