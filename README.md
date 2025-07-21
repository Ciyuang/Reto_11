# RETO 11

## 1. Consulte que hacen los métodos de strings en python:
- endswith 
- startswith 
- isalpha 
- isalnum
- isdigit
- isspace
- istitle
- islower
- isupper
<br>
<br>
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
## 2. Procesar el archivo y extraer:

- Cantidad de vocales
- Cantidad de consonantes
- Listado de las 50 palabras que más se repiten

    **Solucion**
    ```python
    from collections import Counter
    import string
    import urllib.request

    # --- 1. Descargar el archivo ---
    url = "https://www.py4e.com/code3/mbox.txt"
    local = "mbox.txt"
    urllib.request.urlretrieve(url, local)

    # --- 2. Leer y normalizar texto ---
    with open(local, encoding="utf-8") as f:
        texto = f.read().lower()

    # --- 3. Contar vocales y consonantes ---
    vocales = set("aeiou")
    consonantes = set(string.ascii_lowercase) - vocales

    count_v = sum(1 for c in texto if c in vocales)
    count_c = sum(1 for c in texto if c in consonantes)

    # --- 4. Contar palabras ---
    # eliminar puntuación
    texto_sin_punt = texto.translate(str.maketrans("", "", string.punctuation))
    # dividir en lista de palabras
    palabras = texto_sin_punt.split()
    # contar frecuencias
    freq = Counter(palabras)
    top50 = freq.most_common(50)

    # --- 5. Mostrar resultados ---
    print(f"Cantidad de vocales: {count_v}")
    print(f"Cantidad de consonantes: {count_c}\n")

    print("Top 50 palabras más frecuentes:")
    for palabra, cuenta in top50:
        print(f"{palabra}: {cuenta}")
    ```
    **Lo que imprime el code**
    ```
    Cantidad de vocales: 1597835
    Cantidad de consonantes: 2612121

    Top 50 palabras más frecuentes:
    2007: 22447
    from: 21720
    by: 18028
    received: 16176
    with: 12757
    id: 12607
    0500: 11774
    nakamurauitsiupuiedu: 10774
    dec: 9267
    nov: 8988
    sourcecollabsakaiprojectorg: 8985
    for: 7715
    esmtp: 7188
    paploouhiacuk: 7188
    textplain: 5391
    charsetutf8: 5391
    gmt: 4941
    0000: 4932
    thu: 4764
    to: 4566
    tue: 4498
    oct: 4164
    fri: 4007
    mon: 3685
    you: 3621
    date: 3612
    sakai: 3607
    murder: 3594
    mailumichedu: 3594
    cyrus: 3594
    lmtpa: 3594
    localhost: 3594
    127001: 3594
    postfix: 3594
    smtp: 3594
    wed: 3518
    0400: 2910
    the: 2544
    svn: 2537
    23: 2169
    10: 2145
    log: 2100
    site: 1887
    modify: 1884
    this: 1882
    new: 1879
    message: 1842
    was: 1835
    29: 1834
    revision: 1833
    ```
# Autor 🤖
- [Juan Carlos Polania Bolivar](https://github.com/Ciyuang)

