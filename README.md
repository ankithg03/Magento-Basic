# Magento Basic

1. To Go through complete Magento Dashboard(Except email template, and blocks containing blocks, widget, var  as it involves Magento Template Syntax) if your not a BE developer
    
    * If you are going to start with backend start with HTML, PHP, Dynamic Programming and Algorithm


<br>

# Magento Email template
Magento's email templates primarily use **HTML** and **Magento Template Syntax** (a mix of HTML and PHP-like directives) for dynamic content.

### Languages Involved

1. **HTML (HyperText Markup Language)**
   - **Purpose**: Structures and styles the email content.
   - **Usage**: Utilizes HTML tags like `<div>`, `<table>`, `<p>`, and `<a>` to design the layout of the email.

2. **Magento Template Syntax**
   - **Purpose**: Embeds dynamic content and logic within the template.
   - **Usage**: Includes Magento-specific directives, variables, and conditional logic to insert dynamic data such as customer names, order details, etc.

### Markdown Content

Here's a detailed breakdown in Markdown format:

---

## Magento Email Templates

### Languages Involved

Magento's email templates utilize a combination of:

1. **HTML**
2. **Magento Template Syntax**

### 1. HTML

HTML is used for creating the structure and layout of the email. It includes common HTML elements for content formatting.

#### Example

```html
<!DOCTYPE html>
<html>
<head>
    <title>Order Confirmation</title>
</head>
<body>
    <h1>Order Confirmation</h1>
    <p>Dear {{var customer_name}},</p>
    <p>Thank you for your order #{{var order.increment_id}}.</p>
    <p>Total: {{var order.grand_total}}</p>
</body>
</html>
```

- **HTML Tags**: `<html>`, `<head>`, `<body>`, `<h1>`, `<p>`, etc.
- **Purpose**: Defines the visual layout and style of the email.

### 2. Magento Template Syntax

Magento Template Syntax is used to embed dynamic content and logic. This syntax allows the insertion of variables and conditional logic into the email templates.

#### Key Components

- **Variables**: Used to insert dynamic data.
  
  ```html
  {{var order.increment_id}}
  ```

- **Block Directives**: Insert content from CMS blocks or other templates.
  
  ```html
  {{block type="core/template" template="path/to/template.phtml"}}
  ```

- **If Statements**: Conditional rendering based on certain criteria.
  
  ```html
  {{if order.getCustomerIsGuest()}}
    Thank you for your purchase!
  {{else}}
    Thank you for registering!
  {{/if}}
  ```

- **Translations**: Allows for multilingual content.
  
  ```html
  {{trans "Thank you for your purchase!"}}
  ```

#### Example

```html
<!DOCTYPE html>
<html>
<head>
    <title>Order Confirmation</title>
</head>
<body>
    <h1>Order Confirmation</h1>
    <p>Dear {{var customer_name}},</p>
    <p>Thank you for your order #{{var order.increment_id}}.</p>
    <p>Total: {{var order.grand_total}}</p>
    {{if order.getCustomerIsGuest()}}
        <p>Welcome, guest! Enjoy your shopping experience.</p>
    {{else}}
        <p>Thank you for being a valued customer!</p>
    {{/if}}
</body>
</html>
```

- **Dynamic Variables**: `{{var customer_name}}`, `{{var order.increment_id}}`, `{{var order.grand_total}}`
- **Conditional Logic**: `{{if ...}}`, `{{else}}`, `{{/if}}`

### Putting It All Together

Magento email templates combine HTML for layout and styling with Magento Template Syntax for dynamic content. This enables personalized and functional email communications that can adapt to various customer data and interactions.

---