Descripción del Proyecto

Este proyecto implementa un entorno VR básico en escritorio utilizando Godot Engine 4 y el plugin CardboardVR (Cardboard VR Camera3D), que despliega una vista estereoscópica (pantalla dividida en dos ojos) de forma nativa al ejecutar el proyecto en la computadora, sin necesidad de un visor físico.


1. Configuración del entorno de desarrollo

Se creó el proyecto Proyecto_VR en Godot Engine 4.6 (renderizador gl_compatibility, motor de físicas Jolt Physics).
Se integró el plugin CardboardVR en addons/cardboard_vr/, incluyendo sus scripts (cardboard_vr_camera.gd, cardboard_vr.gd), escena de vista (CardboardView.tscn) y shader de distorsión de lente (LensBarrelShader.gdshader).
Se activó el plugin en Proyecto → Configuración del Proyecto → Plugins (visible en project.godot como enabled=PackedStringArray("res://addons/cardboard_vr/plugin.cfg")).
En main.tscn se agregó un nodo CharacterBody3D como jugador, y dentro de él la cámara CardboardVRCamera3D con el script del plugin.
Se configuraron las propiedades de la cámara VR: UseGysroscope = false (control por mouse, ya que se ejecuta en escritorio sin sensores).
Se agregó un MeshInstance3D (PlaneMesh de 30x30) como suelo, DirectionalLight3D para iluminación y WorldEnvironment para el entorno visual.
Se instanció el modelo Untitled.blend seis veces dentro de un nodo contenedor objetos, distribuido en distintas posiciones de la escena para dar contexto visual al entorno.
Se ejecutó el proyecto y se verificó la vista estereoscópica dividida en dos ojos funcionando correctamente en escritorio.

Uso transparente de IA

Consulta 1

Herramienta: Claude
Prompt exacto utilizado:

La estructura inicial del proyecto en Godot
Buscar/verificar el plugin cardboardvr correcto y cómo instalarlo
El .gitignore para Godot
Redactar el README.md con las secciones que piden

Cómo se adaptó la respuesta: Claude verificó en línea la existencia del plugin "CardboardVR" (repositorio CiaNCI-Studio/CardboardVR, compatible con Godot 4) y confirmó que coincidía con el nombre solicitado en la actividad (cardboardvr). Se usaron sus instrucciones de instalación (vía AssetLib del editor) y se generó a partir de su propuesta la estructura de carpetas del proyecto y el archivo .gitignore.

Consulta 2

Herramienta: Claude
Prompt exacto utilizado:

[Subida de proyecto CardboardVR.zip para revisión]

Cómo se adaptó la respuesta: Claude revisó los archivos del proyecto (Main.tscn, player.tscn, project.godot) y detectó que existían dos cámaras CardboardVRCamera3D activas simultáneamente dentro del nodo Player (una en player.tscn y otra agregada directamente en Main.tscn). Se eliminó la cámara duplicada, dejando solo la integrada en player.tscn, siguiendo la recomendación.

Consulta 3

Herramienta: Claude
Prompt exacto utilizado:

Redactar el README.md con las secciones que piden

Cómo se adaptó la respuesta: Claude generó este README.md a partir de la revisión directa del repositorio (git log, project.godot, main.tscn), documentando el procedimiento real seguido, además de detectar que faltaba configurar run/main_scene en project.godot, lo cual se agregó al registro de errores.

(Agrega aquí cualquier otra consulta que hayas hecho a Claude, ChatGPT, Gemini, etc., con el prompt exacto y cómo adaptaste la respuesta.)