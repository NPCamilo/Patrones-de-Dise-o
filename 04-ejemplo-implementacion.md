# Ejemplo práctico: Pedido con estados

Lenguaje: pseudocódigo tipo JavaScript/TypeScript. Adáptalo a tu stack.

## Sin State (lo que quieres evitar)

```javascript
class Pedido {
  constructor() { this.estado = 'pendiente'; }

  pagar() {
    if (this.estado === 'pendiente') {
      this.estado = 'pagado';
      console.log('Pago aceptado');
    } else {
      console.log('No se puede pagar en este estado');
    }
  }

  enviar() {
    if (this.estado === 'pagado') {
      this.estado = 'enviado';
      console.log('Pedido enviado');
    } else {
      console.log('No se puede enviar todavía');
    }
  }
}
```

Problema: cada nuevo estado obliga a tocar todos los métodos. Se vuelve imposible de mantener.

## Con State

```javascript
// Interfaz Estado
class Estado {
  pagar(pedido) { throw new Error('No implementado'); }
  enviar(pedido) { throw new Error('No implementado'); }
  cancelar(pedido) { throw new Error('No implementado'); }
}

// Estados concretos
class Pendiente extends Estado {
  pagar(pedido) {
    pedido.estado = new Pagado();
    console.log('Pago aceptado');
  }
  enviar(pedido) {
    console.log('No se puede enviar: pedido pendiente');
  }
}

class Pagado extends Estado {
  pagar(pedido) {
    console.log('Ya está pagado');
  }
  enviar(pedido) {
    pedido.estado = new Enviado();
    console.log('Pedido enviado');
  }
}

class Enviado extends Estado {
  pagar(pedido) {
    console.log('Ya se envió, no se puede pagar');
  }
  enviar(pedido) {
    console.log('Ya se envió');
  }
}

// Contexto
class Pedido {
  constructor() {
    this.estado = new Pendiente();
  }

  pagar()   { this.estado.pagar(this); }
  enviar()  { this.estado.enviar(this); }
  cancelar() { this.estado.cancelar(this); }
}

// Uso
const p = new Pedido();
p.pagar();   // Pago aceptado
p.enviar();  // Pedido enviado
p.pagar();   // Ya se envió, no se puede pagar
```

## Qué observar

- `Pedido` no sabe si está pendiente, pagado o enviado. Solo delega.
- Cada estado vive en su propia clase. Agregar `Reembolsado` no toca a `Pedido`.
