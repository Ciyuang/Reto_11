# RETO 11

## 1. Consulte que hacen los siguientes métodos de strings en python: endswith, startswith, isalpha, isalnum, isdigit, isspace, istitle, islower, isupper.

1. endswith(sufijo)
    **¿Qué hace?**  
    Verifica si una cadena termina con el texto especificado.

    ```python
    "hola mundo".endswith("mundo")  # True
    "hola mundo".endswith("hola")   # False
    ```

2. startswith(prefijo)
    **¿Qué hace?**  
    Verifica si una cadena empieza con el texto especificado.

    ```python
    "hola mundo".startswith("hola")  # True
    "hola mundo".startswith("mundo") # False

    ```

3. isalpha()
    **¿Qué hace?**  
    Retorna True si todos los caracteres son letras (A-Z o a-z) y no está vacía.

    ```python
    "Python".isalpha()     # True
    "Python3".isalpha()    # False
    "".isalpha()           # False
    ```

4. isalnum()
    **¿Qué hace?**  
    Retorna True si todos los caracteres son alfanuméricos (letras y/o números) y no está vacía.

    ```python
    "Python3".isalnum()    # True
    "Python 3".isalnum()   # False
    "123".isalnum()        # True
    ```

5. isdigit()
    **¿Qué hace?**  
    Retorna True si todos los caracteres son dígitos numéricos (0-9).

    ```python
    "12345".isdigit()    # True
    "12.3".isdigit()     # False
    "uno".isdigit()      # False
    ```

6. isspace()
    **¿Qué hace?**  
    Retorna True si todos los caracteres son espacios en blanco (espacios, tabulaciones, saltos de línea).

    ```python
    "   ".isspace()      # True
    "\t\n ".isspace()    # True
    " a ".isspace()      # False
    ```

7. istitle()
    **¿Qué hace?**  
    Retorna True si cada palabra en la cadena comienza con mayúscula y el resto en minúscula.

    ```python
    "Hola Mundo".istitle()    # True
    "Hola mundo".istitle()    # False
    "hola Mundo".istitle()    # False
    ```

8. islower()
    **¿Qué hace?**  
    Retorna True si todos los caracteres alfabéticos están en minúscula.

    ```python
    "python".islower()    # True
    "Python".islower()    # False
    "123".islower()       # False
    ```

9. `endswith(sufijo)`
    **¿Qué hace?**  
    Retorna True si todos los caracteres alfabéticos están en mayúscula.

    ```python
    "PYTHON".isupper()    # True
    "Python".isupper()    # False
    "123".isupper()       # False
    ```
