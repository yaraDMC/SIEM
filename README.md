In this Splunk project, I will create a realistic lab where I will demonstrate  log collection (Windows, Linux, Firewalls), correlation rule creation (security alerts),  visual dashboards for forensic analysis, and response automation (e.g., blocking malicious IPs).

With Splunk correctly installed, we will run it.

![](https://github.com/yaraDMC/SIEM/blob/main/splunkinicio.png)


 We will upload sample data (attack logs) and download sample logs
as we will use Apache logs simulating attacks:
Create a folder and download the logs.

![](https://github.com/yaraDMC/SIEM/blob/main/descargalogs.png)


y subir los logs en splunk

![](https://github.com/yaraDMC/SIEM/blob/main/subirlogs.png)

y ya subimos los logs y ya los tenemos

![](https://github.com/yaraDMC/SIEM/blob/main/logsee.png)


Búsquedas para Detección de Amenazas
3.1 Detección de Fuerza Bruta (SSH)
SPL Query:
index=main sourcetype=access_combined status=401 | stats count by src_ip | where count > 5



