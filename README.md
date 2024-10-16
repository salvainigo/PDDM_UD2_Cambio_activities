
# Cambio entre pantallas en Android Studio

Guía paso a paso para realizar el cambio entre actividades en Android Studio.


## Paso 1: Crear las actividades
1. Haz clic derecho sobre el paquete de tu proyecto en el explorador de proyectos.
2. Selecciona **New > Activity > Empty Activity**.
3. Dale un nombre a la nueva actividad (por ejemplo, `SecondActivity`).


## Paso 2: Configurar el Intent para el cambio de pantalla
Utiliza el siguiente código en la actividad desde la que quieres cambiar de pantalla:

```java
Intent intent = new Intent(MainActivity.this, SecondActivity.class);
startActivity(intent);
```

Este código crea un `Intent` que especifica que quieres cambiar de `MainActivity` a `SecondActivity` y luego se llama al método `startActivity()` para iniciar la nueva pantalla.

## Paso 3: Configurar la interfaz de usuario
Agrega un botón en el archivo `activity_main.xml`:

```xml
<Button
    android:id="@+id/btnChangeScreen"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="Cambiar Pantalla" />
```

Luego, configura el `OnClickListener` en la actividad:

```java
Button btnChangeScreen = findViewById(R.id.btnChangeScreen);
btnChangeScreen.setOnClickListener(new View.OnClickListener() {
    @Override
    public void onClick(View v) {
        Intent intent = new Intent(MainActivity.this, SecondActivity.class);
        startActivity(intent);
    }
});
```

## Paso 4: Declarar la actividad en el archivo `AndroidManifest.xml`
Verifica que la nueva actividad esté declarada en `AndroidManifest.xml`:

```xml
<activity android:name=".SecondActivity" />
```

## Resumen
1. Crea las actividades necesarias.
2. Usa `Intent` para cambiar de una actividad a otra.
3. Configura un evento (como un botón) para ejecutar el cambio.
4. Declara todas las actividades en el archivo `AndroidManifest.xml`.
