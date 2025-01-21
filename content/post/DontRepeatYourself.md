---
title: "Don't repeat yourself"
date: 2024-01-07T20:44:30+02:00
draft: false
---

# Don't repeat yourself: El Principio DRY

Uno de los principios más importantes en programación es **DRY** (Don't Repeat Yourself). ¿Qué significa? Simplemente que no debes repetir el mismo código una y otra vez. La idea es que cada lógica o regla de negocio tenga una única representación en tu sistema.

## ¿Por qué evitar la repetición?

Imagina que tienes el mismo bloque de código en varias funciones. Si necesitas cambiar algo en ese código, tendrías que actualizarlo en todos esos lugares. Esto puede ser fácil de olvidar y llevar a errores. DRY nos dice que, si algo se repite, es mejor extraerlo y reutilizarlo.

### Ejemplo rápido:

Supón que tienes dos funciones para validar emails:

```python
def validate_user_email(email):
    if "@" not in email:
        raise ValueError("Invalid Email")

def validate_admin_email(email):
    if "@" not in email:
        raise ValueError("Invalid Email")
```

Aquí, estamos repitiendo la misma validación en dos funciones. ¿Por qué no crear una función común que lo haga?

```python
def validate_email(email):
    if "@" not in email:
        raise ValueError("Email inválido")

def validate_user_email(email):
    validate_email(email)

def validate_admin_email(email):
    validate_email(email)
```

Ahora tenemos una única función de validación que se reutiliza en ambas, haciendo el código más limpio y fácil de mantener.

## ¿Por qué es útil DRY?
-Menos errores: Si hay algo que cambiar, solo lo haces una vez.

-Mejor mantenimiento: El código es más fácil de entender y modificar.

-Código más limpio: Al eliminar la repetición, tu código se vuelve más claro.

<br>
En resumen, DRY te ayuda a mantener tu código más limpio, más eficiente y menos propenso a errores. La próxima vez que veas código repetido, recuerda: ¡es hora de aplicar DRY!