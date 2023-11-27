# Biblioteca clsx

**Clsx** es una biblioteca que permite alternar nombres de clases facilmente.

```jsx
import clsx from 'clsx';
 
export default function InvoiceStatus({ status }: { status: string }) {
  return (
    <span
      className={clsx(
        'inline-flex items-center rounded-full px-2 py-1 text-sm', //Esto es fijo
        {
          'bg-gray-100 text-gray-500': status === 'pending',
          'bg-green-500 text-white': status === 'paid',
        }, //Esto es condicional
      )}
    >
    // ...
)}
```