# Zod: TypeScript-First Schema Validation 🚀

![Zod Logo](https://example.com/zod-logo.png)

Welcome to the **Zod** repository! Zod is a powerful library for schema validation in TypeScript. It offers static type inference, ensuring that your data structures align perfectly with your TypeScript types. This means fewer runtime errors and a smoother development experience.

## Table of Contents

- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Examples](#examples)
- [API Reference](#api-reference)
- [Contributing](#contributing)
- [License](#license)
- [Releases](#releases)

## Features

- **Type Safety**: Zod provides runtime validation while ensuring that your TypeScript types are accurate.
- **Schema Validation**: Create schemas for your data models and validate them easily.
- **Static Type Inference**: Automatically infer types from your schemas, reducing boilerplate code.
- **Lightweight**: Zod is designed to be minimal and efficient, making it a great choice for TypeScript projects.

## Installation

To install Zod, use npm or yarn:

```bash
npm install zod
```

or

```bash
yarn add zod
```

## Usage

Here’s a simple example to get you started:

```typescript
import { z } from 'zod';

// Define a schema
const UserSchema = z.object({
  name: z.string(),
  age: z.number().min(0),
});

// Validate data
const result = UserSchema.safeParse({ name: "Alice", age: 30 });

if (result.success) {
  console.log("Valid user:", result.data);
} else {
  console.error("Validation errors:", result.error);
}
```

In this example, we define a `UserSchema` that requires a `name` as a string and an `age` as a non-negative number. The `safeParse` method checks the data against the schema and returns either the validated data or errors.

## Examples

### Basic Schema Validation

```typescript
const ProductSchema = z.object({
  id: z.string(),
  price: z.number().positive(),
});

const productData = { id: "123", price: 25 };

const productResult = ProductSchema.safeParse(productData);

if (productResult.success) {
  console.log("Valid product:", productResult.data);
} else {
  console.error("Validation errors:", productResult.error);
}
```

### Nested Schemas

Zod also supports nested schemas for complex data structures.

```typescript
const OrderSchema = z.object({
  orderId: z.string(),
  products: z.array(ProductSchema),
});

const orderData = {
  orderId: "order-001",
  products: [{ id: "123", price: 25 }],
};

const orderResult = OrderSchema.safeParse(orderData);

if (orderResult.success) {
  console.log("Valid order:", orderResult.data);
} else {
  console.error("Validation errors:", orderResult.error);
}
```

### Custom Validation

You can also create custom validations using the `refine` method.

```typescript
const EmailSchema = z.string().email();

const emailResult = EmailSchema.safeParse("test@example.com");

if (emailResult.success) {
  console.log("Valid email:", emailResult.data);
} else {
  console.error("Validation errors:", emailResult.error);
}
```

## API Reference

Zod provides a rich API for creating and validating schemas. Here are some key components:

- `z.object()`: Creates an object schema.
- `z.string()`: Creates a string schema.
- `z.number()`: Creates a number schema.
- `z.array()`: Creates an array schema.
- `z.union()`: Creates a union schema.
- `z.intersection()`: Creates an intersection schema.
- `z.tuple()`: Creates a tuple schema.
- `refine()`: Adds custom validation logic.

For a complete list of methods and options, please refer to the [official documentation](https://zod.dev/docs).

## Contributing

We welcome contributions! If you'd like to help improve Zod, please follow these steps:

1. Fork the repository.
2. Create a new branch (`git checkout -b feature/YourFeature`).
3. Make your changes and commit them (`git commit -m 'Add some feature'`).
4. Push to the branch (`git push origin feature/YourFeature`).
5. Open a Pull Request.

Please ensure your code adheres to our coding standards and includes tests where applicable.

## License

Zod is open-source software licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

## Releases

For the latest updates and releases, visit the [Releases](https://github.com/Aakanksha011/zod/releases) section. You can download the latest version and execute it in your projects.

![Download Latest Release](https://img.shields.io/badge/Download%20Latest%20Release-Click%20Here-blue)

Feel free to check out the [Releases](https://github.com/Aakanksha011/zod/releases) for more details on what's new!

## Conclusion

Zod simplifies schema validation in TypeScript while ensuring type safety. Its straightforward API makes it easy to use in any TypeScript project. We hope you find Zod useful and look forward to your contributions!

![Zod](https://example.com/zod-image.png)

Thank you for checking out Zod!