# Cómo instalar KairoOS

[← Volver al inicio](../README.md)

## 1. Descarga lo necesario

1. **La ISO de KairoOS:** [KairoOS.iso en MEGA](https://mega.nz/file/wU8ThYAR#Z-4bU1jSiKvKsmQ3q6IeXDBDnu5qX36VfoAp4MXq8Sk). Pesa 8,5 GB.
   - Las cuentas gratis de MEGA tienen un límite de descarga cada pocas horas. Si se para a mitad, espera a que se renueve o descárgala con la app de MEGA, que la reanuda sola.
   - **Comprueba que es la original** (que no se ha dañado ni la ha cambiado nadie). En PowerShell:
     ```powershell
     Get-FileHash "$env:USERPROFILE\Downloads\KairoOS.iso" -Algorithm SHA256
     ```
     Tiene que salir exactamente: `3E6EC0A57F1AF3BFE2FC1C15E82310CBDD7DF5FD13E963536C4F19FB92C466A2`
2. **Rufus:** desde [rufus.ie](https://rufus.ie/), para grabar la ISO en un USB.

## 2. Grábala en un USB

1. Conecta un USB de 16 GB o más. **Se borrará todo lo que tenga.**
2. Abre Rufus, elige el USB y pulsa **SELECCIONAR** para escoger `KairoOS.iso`.
3. Esquema de partición: **GPT**. Sistema de destino: **UEFI**.
4. Pulsa **EMPEZAR**.
   - Si Rufus ofrece opciones de "personalizar la instalación de Windows" (quitar requisitos, cuenta local...), **desmárcalas todas**. KairoOS ya se encarga de eso.

## 3. Instala

1. Arranca el equipo desde el USB. Normalmente se entra con F12, F11, F9 o Esc al encender, según la marca.
2. Sigue el instalador de KairoOS:
   - **Idioma:** español o English.
   - **Disco:** se borrará entero.
   - **Edición:** si tu equipo trae Windows de fábrica, elige la misma, casi siempre **Home**.
   - **Cuenta local:** nombre de usuario y contraseña opcional.
3. El equipo se reinicia y, al entrar por primera vez, verás **"Preparando tu sistema gaming"**. No lo apagues: tarda unos 15-25 minutos y se reinicia solo al terminar.
   - **Con cable de red** se conecta solo.
   - **Con Wi-Fi**, KairoOS te enseña las redes en su pantalla para conectarte.
   - **Sin internet** también se instala; lo que necesita descargarse se hará después.

## 4. El logo de arranque con Secure Boot (solo una vez)

Si tu equipo tiene **Secure Boot** activado, al reiniciar saldrá **una pantalla azul** para aprobar el logo de KairoOS:

1. En "Verification failed", pulsa **Intro** sobre **OK**.
2. Pulsa cualquier tecla enseguida (tienes 5 segundos).
3. Elige **Enroll hash from disk**.
4. Entra en el disco → **EFI** → **HackBGRT** → **grubx64.efi**.
5. Elige **Continue**, luego **Yes** y por último **Reboot**.

Si no lo haces, no pasa nada: el equipo arranca igual con el logo normal, y KairoOS lo vuelve a pedir dos veces más. La pantalla de KairoOS te enseña estos mismos pasos antes de reiniciar.

## 5. ¡A jugar!

- **KairoOS Center** está en el menú Inicio: planes de energía, hercios de la pantalla, interruptores y más.
- **Windows Update** funciona normal. Después de una actualización grande, KairoOS te preguntará si quieres volver a aplicar sus ajustes.
