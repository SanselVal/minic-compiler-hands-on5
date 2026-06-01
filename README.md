# MiniC Analyzer - Hands-on 5

**Autor:** José Antonio Aviña Méndez

**Estudiante:** Uriel Valentin Sánchez Nava

## Mejoras implementadas

### Análisis Léxico (scanner.l)
- Reconocimiento de comentarios de una línea `//`
- Reconocimiento de operadores aritméticos `+ - * /`
- Contador de líneas (`yylineno`)
- Palabra reservada `func`

### Análisis Sintáctico (parser.y)
- Soporte para funciones con `func nombre(a,b)`
- Parámetros sin tipos explícitos
- Expresiones aritméticas con precedencia
- Sentencia `if` simple

### Análisis Semántico
- Tabla de símbolos con campos: nombre, clase, tipo, ámbito, aridad, usado
- Detección de variables declaradas pero no usadas
- Verificación de variables declaradas antes de usarse
- Verificación de macros duplicadas
- Verificación de funciones redeclaradas

## Archivos incluidos
- `scanner.l` - Analizador léxico (Flex)
- `parser.y` - Analizador sintáctico (Bison)
- `correcto.c` - Programa de prueba sin errores
- `errores.c` - Programa de prueba con errores semánticos

## Cómo compilar y ejecutar
```bash
make clean
make
./minic-compiler correcto.c
./minic-compiler errores.c
