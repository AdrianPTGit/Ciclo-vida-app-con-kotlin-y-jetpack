# Ejercicio 1: Mostrar el ciclo de vida de una app Android en consola (Logcat)

## Instrucciones

1. Crea un proyecto con **Jetpack Compose**.

2. La clase principal `MainActivity` implementa la interfaz `DefaultLifecycleObserver` para observar los cambios del ciclo de vida.

3. Muestra los estados en **Logcat**. Para ello se utiliza el comando:

- Log.d(tag: String, msg: String)   , siendo:
- tag  ->  Una cadena corta que identifica el origen del mensaje (por ejemplo, el nombre de tu clase o módulo).
- msg ->  El mensaje que quieres mostrar en el Logcat.

4. Copia el siguiente código en tu editor de Android Studio
```kotlin
import android.os.Bundle
import android.util.Log
import androidx.activity.ComponentActivity
import androidx.activity.compose.setContent
import androidx.compose.material3.*
import androidx.compose.runtime.Composable
import androidx.lifecycle.*

class MainActivity : ComponentActivity(), DefaultLifecycleObserver {

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        Log.d("CicloVida", "onCreate ejecutado")

        lifecycle.addObserver(this)

        setContent {
            MiAppTheme {
                Saludo()
            }//MiAppThemeTheme
        }//setContent
    }//onCreate


```
5. Sobrescribe los métodos de los principales estados . En cada método utiliza Log.d para mostrar un mensaje indicando el estado en el que se encuentra la aplicacion.
6. Ejecuta la aplicación para ver el resultado
