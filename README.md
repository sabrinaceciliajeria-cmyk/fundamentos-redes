# 📡 Fundamentos de Redes: Router, Switch y Hub

---

## 🧩 1. ¿Qué es cada dispositivo?

| Concepto | Definición simple | Nivel técnico (breve) | Ejemplo real (Windows) |
| --- | --- | --- | --- |
| **Router** | Conecta tu PC a otras redes y decide a dónde enviar los datos. | Usa la IP para enviar paquetes fuera de la red local de forma eficiente. | `ping google.com` → tu PC envía la solicitud a internet. |
| **Switch** | Entrega datos solo al dispositivo correcto dentro de la red local. | Usa la MAC address para identificar cada equipo y enviar datos sin saturar la red. | `arp -a` → muestra los PCs conectados al switch. |
| **Hub** | Envía datos a todos los dispositivos sin filtrar, causando saturación. | Funciona por broadcast, generando tráfico innecesario y posibles colisiones. | Varias PCs conectadas a un hub antiguo reciben todos los paquetes. |

---

## ⚙️ 2. ¿Cómo funciona realmente?

**¿Qué hace el router con los paquetes de datos?**  
El router revisa la IP de cada paquete y decide la ruta más rápida para que llegue a otra red o internet. Esto garantiza eficiencia en la comunicación.

**¿Cómo decide un switch a dónde enviar la información?**  
El switch usa la MAC address de destino y entrega los datos solo al dispositivo correcto. Esto optimiza el tráfico dentro de la red local.

**¿Por qué el hub es considerado obsoleto?**  
El hub reenvía todos los paquetes a todos los dispositivos (broadcast). Esto genera colisiones y disminuye la velocidad de la red.

---

## 💻 3. Conexión directa con desarrollo

**¿Qué rol cumple el router cuando haces una petición a una API (`fetch("https://api.miapp.com")`)?**  
El router lleva la petición desde Windows hasta la API por la ruta correcta. Sin él, los datos no llegarían al servidor remoto ni volverían a tu PC.

**¿Por qué un switch es importante en un backend o data center?**  
El switch permite que los servidores y PCs locales se comuniquen rápido. Esto evita saturar la red y mantiene la eficiencia de las aplicaciones.

**¿Qué problemas de red podrían afectar tu aplicación aunque tu código esté “correcto”?**  
Latencia, pérdida de paquetes o caída de conexión pueden impedir que la app funcione. Incluso el código más correcto puede fallar por la red.

---

## 🌍 4. Caso práctico real

**¿Podría ser problema de router? ¿Por qué?**  
Sí, si `ping google.com` desde Windows no responde, el router no está enviando datos a internet correctamente.

**¿Podría ser problema de switch? ¿Por qué?**  
Sí, si `ping servidor_local` falla aunque internet funcione, el switch no entrega datos correctamente en la red local.

**¿Cómo distinguir si es problema de red o de código?**  
CMD (`ping`, `tracert`) revisa la red para identificar fallos. Los logs de la app revisan errores internos del código y su lógica.

---

## 🧪 5. Analogía obligatoria

**Router:** Oficina de correos entre ciudades → decide a qué ciudad enviar tu mensaje. Permite que la información viaje correctamente entre redes distintas.  

**Switch:** Recepcionista que entrega el mensaje al destinatario correcto → solo al PC correcto. Evita que todos reciban datos que no les corresponden.  

**Hub:** Persona que grita el mensaje a todos → todos escuchan aunque no sea para ellos. Esto genera ruido y congestión en la comunicación.

---

## ⚡ 6. BONUS

**Load balancer:** Reparte solicitudes entre varios servidores para no sobrecargar uno solo y mantener la disponibilidad de la aplicación.  

**Cloud (AWS, Azure, etc.):** Routers y switches virtuales permiten que tu app escale sin depender de hardware físico, garantizando disponibilidad global.

---

## 7. Glosario

- **Router:** Dispositivo que conecta diferentes redes y dirige paquetes según su IP.  
- **Switch:** Dispositivo que conecta equipos dentro de la misma red y entrega datos solo al destinatario correcto.  
- **Hub:** Dispositivo que envía datos a todos los dispositivos de la red, causando tráfico innecesario.  
- **IP (Internet Protocol):** Dirección única de un dispositivo en la red que permite identificarlo y enrutar sus paquetes.  
- **MAC address:** Identificador único de la tarjeta de red de un dispositivo.  
- **Paquete de datos:** Unidad de información enviada por la red.  
- **Ping:** Herramienta para comprobar si un dispositivo responde en la red.  
- **Tracert (traceroute):** Herramienta para identificar la ruta que siguen los paquetes hasta un destino.  
- **Latencia:** Tiempo que tarda un paquete en ir del origen al destino.  
- **Load balancer:** Sistema que reparte la carga entre varios servidores.  
- **Cloud:** Infraestructura virtual para escalar aplicaciones sin depender de hardware físico.****

- ---

## 8. Diagrama visual de red

<img width="275" height="183" alt="image" src="https://github.com/user-attachments/assets/fb36a225-d138-4593-a722-41f0da8213a0" />

**Descripción:**

- **Router (azul, arriba):** conecta la red local con internet u otras redes.  
- **Switch (azul, derecha):** entrega datos solo al dispositivo correcto dentro de la red local.  
- **Hub (verde, izquierda):** envía datos a todos los dispositivos sin filtrar, generando tráfico innecesario.  
- **Servidores y PCs:** representan los equipos conectados a la LAN, recibiendo datos según si están en switch o hub.

