Crear la GVR Camera Rig

Durante este paso, crearemos la cámara VR incluyendo el GvrEditorEmulator en la
escena y configurando la cámara.
1. Agregue el objeto prefab GvrEditorEmulator a la escena.

![image](https://user-images.githubusercontent.com/49041539/126507184-cbcc70ca-3a74-4b70-96fa-751b003d8961.png)

2. Convierta el objeto Main Camera en un elemento hijo del objeto
GvrEditorEmulator.
![image](https://user-images.githubusercontent.com/49041539/126507348-a54a8b89-a4a7-4728-9c2a-d75cc21be0ad.png)

3. Restablece el componente Transformar del objeto Main Camera.

![image](https://user-images.githubusercontent.com/49041539/126507412-fa780791-6847-4626-90b3-2193494fb1e4.png)

4. Mueva el objeto GvrEditorEmulator a una ubicación conveniente para el
desarrollo, por ejemplo, Posición: 0, 3, 35 y Rotación: 0, 180, 0.

![image](https://user-images.githubusercontent.com/49041539/126507988-31f03c93-9e0e-4cb4-ab90-c7b58aa5736f.png)

5. Ingrese al modo de juego y use Alt + Mouse y Ctrl + Mouse para rotar e inclinar
el ángulo de visión de la cámara.

![image](https://user-images.githubusercontent.com/49041539/126508032-01e59a32-b03f-467a-bd50-44873620f97b.png)

Preparando la escena para la interacción
Durante este paso, prepararemos la escena para la interacción configurando el puntero, el
emisor de rayos y el sistema de eventos, y luego probaremos el sistema de punto de
referencia incluido (waypoint).

1. Agregue el objeto prefab GvrReticlePointer a la escena como elemento
secundario del objeto del Main Camera.
![image](https://user-images.githubusercontent.com/49041539/126509296-7560e9a1-8dfc-4ec7-ae04-2144795fc3d4.png)
2. Aumente el valor de Distancia máxima de retícula para el GvrReticlePointer del
valor predeterminado de 10 a 20.
![image](https://user-images.githubusercontent.com/49041539/126509349-447ce873-cf1b-4481-8ee1-05d2d6b98a3e.png)
3. Agregue el script GvrPointerPhysicsRaycaster como componente en el objeto
Main Camera.
![image](https://user-images.githubusercontent.com/49041539/126509316-b09a39c3-15fc-4cac-a6d8-4e45923c57bb.png)
4. Agregue el objeto prefab GvrEventSystem a la escena.
![image](https://user-images.githubusercontent.com/49041539/126509412-90240cd7-29a9-42ca-b89e-cba984737f77.png)
5. Ingrese al modo de juego y navegue por la escena haciendo clic en los puntos de
referencia.
![image](https://user-images.githubusercontent.com/49041539/126509372-dc23ab4e-8c70-4aa4-9a34-aa4e70c4109b.png)
![image](https://user-images.githubusercontent.com/49041539/126509393-5e7865e6-9526-475c-9500-779f3ba9705b.png)
![image](https://user-images.githubusercontent.com/49041539/126509419-2ea7eb78-c6d7-4ba9-9093-a81a3d954727.png)

Hacer que los objetos del juego sean interactivos
Durante este paso haremos que la Moneda, la Llave y la Puerta sean interactivas
añadiéndoles componentes de disparadores y eventos.

1. Localiza y selecciona el objeto Coin en la jerarquía.
![image](https://user-images.githubusercontent.com/49041539/126509626-18ae53eb-2e54-4f1e-8a35-58f806b2fdd8.png)

2. Verifique que tenga un componente Collider.
![image](https://user-images.githubusercontent.com/49041539/126509704-9fe9d47c-fc2c-4f8d-a528-d70574510d8d.png)

3. Agregue el script Coin proporcionado como componente.
![image](https://user-images.githubusercontent.com/49041539/126509735-eaba5f35-39db-4a10-8cdf-64b2aa97fed7.png)

4. Agregue un dispardor de evento (Event Trigger) como componente.
![image](https://user-images.githubusercontent.com/49041539/126509655-23c0ef7e-90c8-4315-9c09-a8e93384fa73.png)

5. Agregue el evento PointerClick al componente Event Trigger.
![image](https://user-images.githubusercontent.com/49041539/126509685-d34fc028-7fca-4242-8e3b-1b1a5341e840.png)

6. Asigne el componente del script Coin al campo de objeto del evento PointerClick.
![image](https://user-images.githubusercontent.com/49041539/126509792-9540274b-acd2-48d6-ab3b-c7af68ba985c.png)

7. Asigne el método Coin.OnCoinClicked () como la función para el evento PointerClick.
![image](https://user-images.githubusercontent.com/49041539/126509759-fbdf4ed4-1771-43aa-b467-d4ae8b6d205f.png)

8. Ingrese al modo de juego, haga clic en la moneda y verifique que el mensaje 'Coin.OnCoinClicked ()' esté impreso en la ventana de la consola.
![image](https://user-images.githubusercontent.com/49041539/126509774-f81f9cd9-0e88-4ea1-b5e4-852a08f3c37e.png)

9. Repita el mismo proceso para el objeto del juego Key pero use el script Key y el método Key.OnKeyClicked ().
![image](https://user-images.githubusercontent.com/49041539/126509892-77e0449e-59a4-45b0-9684-e438865508ce.png)

10. Repita el mismo proceso para el primer objeto principal del juego de Puerta, pero use el script de Puerta y el método Door.OnDoorClicked ().
![image](https://user-images.githubusercontent.com/49041539/126509823-d6854efb-6eac-440c-9bd1-6e6bfdc4a8e5.png)

Hacer la interfaz de usuario interactiva
Durante este paso, haremos que el objeto SignPost sea interactivo al agregarle componentes de disparadores y eventos. El proceso es casi idéntico al que hicimos con la
moneda, la llave y la puerta en el paso anterior, pero no necesitamos un colisionador para interactuar con los objetos del juego de la interfaz de usuario. En su lugar, debemos
verificar que el objeto del juego Canvas tenga un componente Graphic Raycaster, y debido a que estamos usando GVR, reemplazaremos el Graphic Raycaster de Unity con el GvrPointerGraphicRaycaster de Google VR.

Anexo (Pantallazos funcionamiento)

![image](https://user-images.githubusercontent.com/49041539/126510220-5a6499ee-07a3-48c1-8be7-8b8b56754e4b.png)

![image](https://user-images.githubusercontent.com/49041539/126510258-8b5336dd-fde1-4b67-b0cf-a92b1ea1422b.png)

![image](https://user-images.githubusercontent.com/49041539/126510239-92e5e0ff-c7e0-4795-ac14-b0171a0270f0.png)

En el informe se debe incluir la información de GitHub (usuario y URL del repositorio de la práctica)
User: dleont
Link: https://github.com/dleont/Practica08-LaberintoVR

RESULTADO(S) OBTENIDO(S):
• Se desarrolla e integra módulos interactivos virtuales de forma manual simulando un laberinto.

CONCLUSIONES:
• Al finalizar con la práctica se logra implementar escenarios de realidad virtual usando la herramienta Unity de tal forma que aprendimos a usar las animaciones, iteraciones, etc.

Nombre: Darwin Leòn.
Firma: ![image](https://user-images.githubusercontent.com/49041539/126510407-f1cd20b4-c72d-4bce-9484-fe5db0d369a3.png)
