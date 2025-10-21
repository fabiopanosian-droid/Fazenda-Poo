class Animal:
    def __init__(self, nome, idade):
        self.nome = nome
        self.idade = idade

    def emitir_som(self):
        return "O animal emite um som."

    def apresentar(self):
        return f"Olá, sou {self.nome} e tenho {self.idade} anos."


class Cachorro(Animal):
    def __init__(self, nome, idade, raca):
        super().__init__(nome, idade)
        self.raca = raca

    def emitir_som(self):
        return "Au! Au!"


class Gato(Animal):
    def __init__(self, nome, idade, cor_pelo):
        super().__init__(nome, idade)
        self.cor_pelo = cor_pelo

    def emitir_som(self):
        return "Miau!"


class Vaca(Animal):
    def __init__(self, nome, idade, producao_leite_litros):
        super().__init__(nome, idade)
        self.__producao_leite_litros = producao_leite_litros

    def emitir_som(self):
        return "Muuu!"

    def obter_producao_leite(self):
        return self.__producao_leite_litros

    def registrar_ordenha(self, litros):
        self.__producao_leite_litros = litros


# Teste e Demonstração

rex = Cachorro("Rex", 3, "Labrador")
mimi = Gato("Mimi", 5, "Branco")
mimosa = Vaca("Mimosa", 7, 25.5)

# Apresentação
print(rex.apresentar())
print(mimi.apresentar())
print(mimosa.apresentar())

# Sons
print(rex.emitir_som())
print(mimi.emitir_som())
print(mimosa.emitir_som())

# Encapsulamento - Vaca
print(f"Produção atual de leite: {mimosa.obter_producao_leite()} litros")
mimosa.registrar_ordenha(28.0)
print(f"Produção após ordenha: {mimosa.obter_producao_leite()} litros")
