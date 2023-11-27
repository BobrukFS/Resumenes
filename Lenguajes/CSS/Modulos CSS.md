# Modulos CSS

Los módulos CSS le permiten aplicar CSS a un componente creando automáticamente nombres de clase únicos, por lo que no tiene que preocuparse también por las colisiones de estilos.

```css
.shape {
  height: 0;
  width: 0;
  border-bottom: 30px solid black;
  border-left: 20px solid transparent;
  border-right: 20px solid transparent;
}

/*En el react se pondria*/
import styles from '@/app/ui/home.module.css';
//...
<div className="flex flex-col justify-center gap-6 rounded-lg bg-gray-50 px-6 py-10 md:w-2/5 md:px-20">
    <div className={styles.shape}></div>;
// ...

```