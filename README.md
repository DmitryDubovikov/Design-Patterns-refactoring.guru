# Design-Patterns-refactoring.guru

## Порождающие

### Фабрика

#### class Creator(ABC)

**@abstractmethod**
**def factory_method** будет возвращать объект класса Product. Но это не основная задача класса Creator.

**def some_operation** какая-то бизнес-логика, связанная с объектом Product.

#### class Product(ABC)

    @abstractmethod
    def operation(self) -> str:
        pass

#### class ConcreteCreator1(Creator)
    def factory_method(self) -> Product:
        return ConcreteProduct1()
конкретный класс, возвращает конкретный продукт, но в тайпхинте указываем абстрактный продукт.


def client_code(creator: Creator) -> None:

    print(
        f"Client: I'm not aware of the creator's class, but it still works.\n"
        f"{creator.some_operation()}",
        end="",
    )
