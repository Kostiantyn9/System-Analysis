# Розділ 7. Модель даних

## 7.1 Основні сутності та атрибути

| Сутність       | Атрибути                                                                 |
|----------------|--------------------------------------------------------------------------|
| User           | id, name, email, password, role                                          |
| Product        | id, name, description, price, stock, category_id, brand_id               |
| Category       | id, name                                                                 |
| Brand          | id, name                                                                 |
| Basket         | id, user_id                                                              |
| BasketItem     | id, basket_id, product_id, quantity                                      |
| Order          | id, user_id, total_price, status, created_at, updated_at                 |
| OrderItem      | id, order_id, product_id, quantity, price                                |

---

## 7.2 Зв’язки між сутностями

- User 1 - 1 Basket  
- Basket 1 - N BasketItem  
- BasketItem 1 - 1 Product  
- User 1 - N Order  
- Order 1 - N OrderItem  
- OrderItem N - 1 Product  
- Product N - 1 Category  
- Product N - 1 Brand  
- Category N - N Brand

---

## 7.3 ER-діаграма / UML-діаграма класів

![ER-діаграма](../Img/UML/entity_diagram.png)

**Пояснення:**  
- Клас `User` відповідає покупцям та адміністраторам  
- `Basket` і `BasketItem` моделюють кошик покупця  
- `Order` і `OrderItem` моделюють оформлення замовлень  
- `Product`, `Category` і `Brand` відображають структуру каталогу товарів