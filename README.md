1:class Escola:
    def init(self, nome, endereco):
        self.__nome = nome  
        self.__endereco = endereco  

    # Getter para o atributo nome
    def get_nome(self):
        return self.__nome

    # Setter para o atributo nome
    def set_nome(self, nome):
        self.__nome = nome

    # Getter para o atributo endereco
    def get_endereco(self):
        return self.__endereco

    # Setter para o atributo endereco
    def set_endereco(self, endereco):
        self.__endereco = endereco
Testando a classe Escola:
python
Copiar

escola1 = Escola("Escola ABC", "Rua das Flores, 123")


print("Nome da escola:", escola1.get_nome())
print("Endereço da escola:", escola1.get_endereco())


escola1.set_nome("Escola XYZ")
escola1.set_endereco("Avenida Central, 456")

print("Novo nome da escola:", escola1.get_nome())
print("Novo endereço da escola:", escola1.get_endereco())

2:class Escola:
    def _init_(self, nome, endereco):
        self.__nome = nome  
        self.__endereco = endereco  


    def get_nome(self):
        return self.__nome

 
    def set_nome(self, nome):
        self.__nome = nome

    def get_endereco(self):
        return self.__endereco

    def set_endereco(self, endereco):
        self.__endereco = endereco
class Curso(Escola):
    def _init_(self, nome, endereco, cargaHoraria):
        # Chamando o construtor da classe base (Escola)
        super()._init_(nome, endereco)
        self.__cargaHoraria = cargaHoraria  
 
    def get_cargaHoraria(self):
        return self.__cargaHoraria

    def set_cargaHoraria(self, cargaHoraria):
        self.__cargaHoraria = cargaHoraria
        # Criando uma instância da classe Curso
curso1 = Curso("Curso de Python", "Avenida dos Programadores, 101", 120)


print("Nome da escola:", curso1.get_nome())
print("Endereço da escola:", curso1.get_endereco())
print("Carga horária do curso:", curso1.get_cargaHoraria())

curso1.set_nome("Curso de Java")
curso1.set_endereco("Rua da Tecnologia, 200")
curso1.set_cargaHoraria(150)

print("Novo nome do curso:", curso1.get_nome())
print("Novo endereço do curso:", curso1.get_endereco())
print("Nova carga horária do curso:", curso1.get_cargaHoraria())

3:class Escola:
    def _init_(self, nome, endereco):
        self.__nome = nome  # Atributo privado
        self.__endereco = endereco  # Atributo privado

    def get_nome(self):
        return self.__nome

 
    def set_nome(self, nome):
        self.__nome = nome


    def get_endereco(self):
        return self.__endereco

    def set_endereco(self, endereco):
        self.__endereco = endereco

class Curso(Escola):
    def _init_(self, nome, endereco, cargaHoraria):
        # Chamando o construtor da classe base (Escola)
        super()._init_(nome, endereco)
        self.__cargaHoraria = cargaHoraria  # Atributo privado específico de Curso

    # Getter para o atributo cargaHoraria
    def get_cargaHoraria(self):
        return self.__cargaHoraria

    # Setter para o atributo cargaHoraria
    def set_cargaHoraria(self, cargaHoraria):
        self.__cargaHoraria = cargaHoraria

    # Método exibirInformacoes - exibe nome, endereço e carga horária
    def exibirInformacoes(self):
        print(f"Nome: {self.get_nome()}")
        print(f"Endereço: {self.get_endereco()}")
        print(f"Carga Horária: {self.get_cargaHoraria()} horas")
class CursoTecnico(Curso):
    def _init_(self, nome, endereco, cargaHoraria, modalidade):
        # Chamando o construtor da classe base (Curso)
        super()._init_(nome, endereco, cargaHoraria)
        self.__modalidade = modalidade  # Atributo privado específico de CursoTecnico

    # Getter para o atributo modalidade
    def get_modalidade(self):
        return self.__modalidade

    # Setter para o atributo modalidade
    def set_modalidade(self, modalidade):
        self.__modalidade = modalidade

    # Sobrescrevendo o método exibirInformacoes para adicionar a modalidade
    def exibirInformacoes(self):
        super().exibirInformacoes()  # Chama o método da classe base (Curso)
        print(f"Modalidade: {self.get_modalidade()}")
# Criando uma instância da classe Curso
curso1 = Curso("Curso de Python", "Avenida dos Programadores, 101", 120)

# Exibindo as informações do curso
print("Informações do Curso:")
curso1.exibirInformacoes()

# Criando uma instância da classe CursoTecnico
curso_tecnico = CursoTecnico("Curso Técnico em Redes", "Rua da Tecnologia, 200", 200, "Presencial")

# Exibindo as informações do curso técnico (sobrescrita do método)
print("\nInformações do Curso Técnico:")
curso_tecnico.exibirInformacoes()

4:class Escola:
    def _init_(self, nome, endereco):
        self.__nome = nome  # Atributo privado
        self.__endereco = endereco  # Atributo privado

    # Getter para o atributo nome
    def get_nome(self):
        return self.__nome

    # Setter para o atributo nome
    def set_nome(self, nome):
        self.__nome = nome

    # Getter para o atributo endereco
    def get_endereco(self):
        return self.__endereco

    # Setter para o atributo endereco
    def set_endereco(self, endereco):
        self.__endereco = endereco
class Curso(Escola):
    def _init_(self, nome, endereco, cargaHoraria):
        # Chamando o construtor da classe base (Escola) para inicializar nome e endereco
        super()._init_(nome, endereco)
        self.__cargaHoraria = cargaHoraria  # Atributo privado específico de Curso

    # Getter para o atributo cargaHoraria
    def get_cargaHoraria(self):
        return self.__cargaHoraria

    # Setter para o atributo cargaHoraria
    def set_cargaHoraria(self, cargaHoraria):
        self.__cargaHoraria = cargaHoraria

    # Método exibirInformacoes - exibe nome, endereço e carga horária
    def exibirInformacoes(self):
        print(f"Nome: {self.get_nome()}")
        print(f"Endereço: {self.get_endereco()}")
        print
class CursoTecnico(Curso):
    def _init_(self, nome, endereco, cargaHoraria, modalidade):
        # Chamando o construtor da classe base (Curso) para inicializar nome, endereco e cargaHoraria
        super()._init_(nome, endereco, cargaHoraria)
        self.__modalidade = modalidade  # Atributo privado específico de CursoTecnico

    # Getter para o atributo modalidade
    def get_modalidade(self):
        return self.__modalidade

    # Setter para o atributo modalidade
    def set_modalidade(self, modalidade):
        self.__modalidade = modalidade

    # Sobrescrevendo o método exibirInformacoes para adicionar a modalidade
    def exibirInformacoes(self):
        super().exibirInformacoes()  # Chama o método da classe base (Curso)
        print(f"Modalidade: {self.get_modalidade()}")
# Criando uma instância da classe Curso
curso1 = Curso("Curso de Python", "Avenida dos Programadores, 101", 120)

# Exibindo as informações do curso
print("Informações do Curso:")
curso1.exibirInformacoes()

# Criando uma instância da classe CursoTecnico
curso_tecnico = CursoTecnico("Curso Técnico em Redes", "Rua da Tecnologia, 200", 200, "Presencial")

# Exibindo as informações do curso técnico (sobrescrita do método)
print("\nInformações do Curso Técnico:")
curso_tecnico.exibirInformacoes()

5:class Escola:
    def _init_(self, nome, endereco):
        self.__nome = nome  # Atributo privado
        self.__endereco = endereco  # Atributo privado

    # Getter para o atributo nome
    def get_nome(self):
        return self.__nome

    # Setter para o atributo nome
    def set_nome(self, nome):
        self.__nome = nome

    # Getter para o atributo endereco
    def get_endereco(self):
        return self.__endereco

    # Setter para o atributo endereco
    def set_endereco(self, endereco):
        self.__endereco = endereco
class Curso(Escola):
    def _init_(self, nome, endereco, cargaHoraria):
        # Chamando o construtor da classe base (Escola) para inicializar nome e endereco
        super()._init_(nome, endereco)
        self.__cargaHoraria = cargaHoraria  # Atributo privado específico de Curso

    # Getter para o atributo cargaHoraria
    def get_cargaHoraria(self):
        return self.__cargaHoraria

    # Setter para o atributo cargaHoraria
    def set_cargaHoraria(self, cargaHoraria):
        self.__cargaHoraria = cargaHoraria

    # Método exibirInformacoes - exibe nome, endereço e carga horária
    def exibirInformacoes(self):
        print(f"Nome: {self.get_nome()}")
        print(f"Endereço: {self.get_endereco()}")
        print(f"Carga Horária: {self.get_cargaHoraria()} horas")
class CursoTecnico(Curso):
    def _init_(self, nome, endereco, cargaHoraria, modalidade):
        # Chamando o construtor da classe base (Curso) para inicializar nome, endereco e cargaHoraria
        super()._init_(nome, endereco, cargaHoraria)
        self.__modalidade = modalidade  # Atributo privado específico de CursoTecnico

    # Getter para o atributo modalidade
    def get_modalidade(self):
        return self.__modalidade

    # Setter para o atributo modalidade
    def set_modalidade(self, modalidade):
        self.__modalidade = modalidade

    # Sobrescrevendo o método exibirInformacoes para adicionar a modalidade
    def exibirInformacoes(self):
        super().exibirInformacoes() 
        print(f"Modalidade: {self.get_modalidade()}")
class Main:
    @staticmethod
    def main():
       
        curso1 = Curso("Curso de Python", "Avenida dos Programadores, 101", 120)

        print("Informações do Curso:")
        curso1.exibirInformacoes()

        
        curso_tecnico = CursoTecnico("Curso Técnico em Redes", "Rua da Tecnologia, 200", 200, "Presencial")

        print("\nInformações do Curso Técnico:")
        curso_tecnico.exibirInformacoes()

# Chamando o método main
if _name_ == "_main_":
    Main.main()

6:class Escola:
    def _init_(self, nome, endereco):
        self.__nome = nome  # Atributo privado
        self.__endereco = endereco  # Atributo privado

    # Getter para o atributo nome
    def get_nome(self):
        return self.__nome

    # Setter para o atributo nome
    def set_nome(self, nome):
        self.__nome = nome

    # Getter para o atributo endereco
    def get_endereco(self):
        return self.__endereco

    # Setter para o atributo endereco
    def set_endereco(self, endereco):
        self.__endereco = endereco
class Curso(Escola):
    def _init_(self, nome, endereco, cargaHoraria):
        # Chamando o construtor da classe base (Escola) para inicializar nome e endereco
        super()._init_(nome, endereco)
        self.__cargaHoraria = cargaHoraria  # Atributo privado específico de Curso

    # Getter para o atributo cargaHoraria
    def get_cargaHoraria(self):
        return self.__cargaHoraria

    # Setter para o atributo cargaHoraria (verificação de valor maior que zero)
    def set_cargaHoraria(self, cargaHoraria):
        if cargaHoraria > 0:
            self.__cargaHoraria = cargaHoraria
        else:
            print("Erro: A carga horária deve ser maior que zero!")

    # Método exibirInformacoes - exibe nome, endereço e carga horária
    def exibirInformacoes(self):
        print(f"Nome: {self.get_nome()}")
        print(f"Endereço: {self.get_endereco()}")
        print(f"Carga Horária: {self.get_cargaHoraria()} horas")
class CursoTecnico(Curso):
    def _init_(self, nome, endereco, cargaHoraria, modalidade):
        # Chamando o construtor da classe base (Curso) para inicializar nome, endereco e cargaHoraria
        super()._init_(nome, endereco, cargaHoraria)
        self.__modalidade = modalidade  # Atributo privado específico de CursoTecnico

    # Getter para o atributo modalidade
    def get_modalidade(self):
        return self.__modalidade

    # Setter para o atributo modalidade
    def set_modalidade(self, modalidade):
        self.__modalidade = modalidade

    # Sobrescrevendo o método exibirInformacoes para adicionar a modalidade
    def exibirInformacoes(self):
        super().exibirInformacoes()  # Chama o método da classe base (Curso)
        print(f"Modalidade: {self.get_modalidade()}")
class Main:
    @staticmethod
    def main():
        # Criando uma instância da classe Curso
        curso1 = Curso("Curso de Python", "Avenida dos Programadores, 101", 120)

        # Exibindo as informações do curso
        print("Informações do Curso:")
        curso1.exibirInformacoes()

        # Testando o setter de cargaHoraria com valor negativo
        print("\nTentando definir carga horária negativa:")
        curso1.set_cargaHoraria(-50)  # Deveria mostrar um erro

        # Testando o setter de cargaHoraria com valor válido
        print("\nDefinindo carga horária positiva:")
        curso1.set_cargaHoraria(150)
        curso1.exibirInformacoes()  # Exibindo informações novamente após alteração

        # Criando uma instância da classe CursoTecnico
        curso_tecnico = CursoTecnico("Curso Técnico em Redes", "Rua da Tecnologia, 200", 200, "Presencial")

        # Exibindo as informações do curso técnico (sobrescrita do método)
        print("\nInformações do Curso Técnico:")
        curso_tecnico.exibirInformacoes()

# Chamando o método main
if _name_ == "_main_":
    Main.main()

7:class Escola:
    def _init_(self, nome, endereco):
        self.__nome = nome  # Atributo privado
        self.__endereco = endereco  # Atributo privado

    # Getter para o atributo nome
    def get_nome(self):
        return self.__nome

    # Setter para o atributo nome
    def set_nome(self, nome):
        self.__nome = nome

    # Getter para o atributo endereco
    def get_endereco(self):
        return self.__endereco

    # Setter para o atributo endereco
    def set_endereco(self, endereco):
        self.__endereco = endereco
class Curso(Escola):
    def _init_(self, nome, endereco, cargaHoraria):
        # Chamando o construtor da classe base (Escola) para inicializar nome e endereco
        super()._init_(nome, endereco)
        self.__cargaHoraria = cargaHoraria  # Atributo privado específico de Curso

    # Getter para o atributo cargaHoraria
    def get_cargaHoraria(self):
        return self.__cargaHoraria

    # Setter para o atributo cargaHoraria (verificação de valor maior que zero)
    def set_cargaHoraria(self, cargaHoraria):
        if cargaHoraria > 0:
            self.__cargaHoraria = cargaHoraria
        else:
            print("Erro: A carga horária deve ser maior que zero!")

    # Método exibirInformacoes - exibe nome, endereço e carga horária
    def exibirInformacoes(self):
        print(f"Nome: {self.get_nome()}")
        print(f"Endereço: {self.get_endereco()}")
        print(f"Carga Horária: {self.get_cargaHoraria()} horas")
class CursoTecnico(Curso):
    def _init_(self, nome, endereco, cargaHoraria, modalidade):
        # Chamando o construtor da classe base (Curso) para inicializar nome, endereco e cargaHoraria
        super()._init_(nome, endereco, cargaHoraria)
        self.__modalidade = modalidade  # Atributo privado específico de CursoTecnico

    # Getter para o atributo modalidade
    def get_modalidade(self):
        return self.__modalidade

    # Setter para o atributo modalidade
    def set_modalidade(self, modalidade):
        self.__modalidade = modalidade

    # Sobrescrevendo o método exibirInformacoes para adicionar a modalidade
    def exibirInformacoes(self):
        # Chamando o método exibirInformacoes da classe Curso (superclasse)
        super().exibirInformacoes()  # Isso chama o método da classe Curso
        print(f"Modalidade: {self.get_modalidade()}")
   class Main:
    @staticmethod
    def main():
        # Criando uma instância da classe Curso
        curso1 = Curso("Curso de Python", "Avenida dos Programadores, 101", 120)

        # Exibindo as informações do curso
        print("Informações do Curso:")
        curso1.exibirInformacoes()

        # Criando uma instância da classe CursoTecnico
        curso_tecnico = CursoTecnico("Curso Técnico em Redes", "Rua da Tecnologia, 200", 200, "Presencial")

        # Exibindo as informações do curso técnico (sobrescrita do método)
        print("\nInformações do Curso Técnico:")
        curso_tecnico.exibirInformacoes()

# Chamando o método main
if _name_ == "_main_":
    Main.main()
8:from abc import ABC, abstractmethod

class Escola(ABC):
    def _init_(self, nome, endereco):
        self.__nome = nome  # Atributo privado
        self.__endereco = endereco  # Atributo privado

    # Getter para o atributo nome
    def get_nome(self):
        return self.__nome

    # Setter para o atributo nome
    def set_nome(self, nome):
        self.__nome = nome

    # Getter para o atributo endereco
    def get_endereco(self):
        return self.__endereco

    # Setter para o atributo endereco
    def set_endereco(self, endereco):
        self.__endereco = endereco

    # Método abstrato que deve ser implementado nas classes filhas
    @abstractmethod
    def calcularMensalidade(self):
        pass
class Curso(Escola):
    def _init_(self, nome, endereco, cargaHoraria):
        super()._init_(nome, endereco)
        self.__cargaHoraria = cargaHoraria  

    # Getter para o atributo cargaHoraria
    def get_cargaHoraria(self):
        return self.__cargaHoraria

    # Setter para o atributo cargaHoraria
    def set_cargaHoraria(self, cargaHoraria):
        if cargaHoraria > 0:
            self.__cargaHoraria = cargaHoraria
        else:
            print("Erro: A carga horária deve ser maior que zero!")

    # Implementação do método calcularMensalidade
    def calcularMensalidade(self):
        # Exemplo: Mensalidade básica de 500 reais
        return 500
class CursoTecnico(Curso):
    def _init_(self, nome, endereco, cargaHoraria, modalidade):
        super()._init_(nome, endereco, cargaHoraria)
        self.__modalidade = modalidade  

    # Getter para o atributo modalidade
    def get_modalidade(self):
        return self.__modalidade

    # Setter para o atributo modalidade
    def set_modalidade(self, modalidade):
        self.__modalidade = modalidade

    # Sobrescrevendo o método calcularMensalidade com acréscimo baseado na carga horária
    def calcularMensalidade(self):
        mensalidade_base = super().calcularMensalidade()  # Chama a implementação de Curso
        # Suponha que a cada 10 horas de carga horária, aumente 50 reais na mensalidade
        acréscimo = (self.get_cargaHoraria() // 10) * 50
        return mensalidade_base + acréscimo

9:from abc import ABC, abstractmethod

class Certificavel(ABC):
    @abstractmethod
    def emitirCertificado(self):
        pass
from abc import ABC, abstractmethod

class Escola(ABC):
    def _init_(self, nome, endereco):
        self.__nome = nome  # Atributo privado
        self.__endereco = endereco  # Atributo privado

    # Getter para o atributo nome
    def get_nome(self):
        return self.__nome

    # Setter para o atributo nome
    def set_nome(self, nome):
        self.__nome = nome

    # Getter para o atributo endereco
    def get_endereco(self):
        return self.__endereco

    # Setter para o atributo endereco
    def set_endereco(self, endereco):
        self.__endereco = endereco

    # Método abstrato para calcular a mensalidade
    @abstractmethod
    def calcularMensalidade(self):
        pass
class Curso(Escola, Certificavel):
    def _init_(self, nome, endereco, cargaHoraria):
        super()._init_(nome, endereco)
        self.__cargaHoraria = cargaHoraria  # Atributo privado específico de Curso

    # Getter para o atributo cargaHoraria
    def get_cargaHoraria(self):
        return self.__cargaHoraria

    # Setter para o atributo cargaHoraria
    def set_cargaHoraria(self, cargaHoraria):
        if cargaHoraria > 0:
            self.__cargaHoraria = cargaHoraria
        else:
            print("Erro: A carga horária deve ser maior que zero!")

    # Implementação do método calcularMensalidade
    def calcularMensalidade(self):
        return 500  # Mensalidade padrão de 500 reais

    # Implementação do método emitirCertificado (da interface Certificavel)
    def emitirCertificado(self):
        return f"Certificado de conclusão de {self.get_nome()} - Carga Horária: {self.get_cargaHoraria()} horas."
class CursoTecnico(Curso):
    def _init_(self, nome, endereco, cargaHoraria, modalidade):
        super()._init_(nome, endereco, cargaHoraria)
        self.__modalidade = modalidade  # Atributo privado específico de CursoTecnico

    # Getter para o atributo modalidade
    def get_modalidade(self):
        return self.__modalidade

    # Setter para o atributo modalidade
    def set_modalidade(self, modalidade):
        self.__modalidade = modalidade

    # Sobrescrevendo o método calcularMensalidade
    def calcularMensalidade(self):
        mensalidade_base = super().calcularMensalidade()
        acréscimo = (self.get_cargaHoraria() // 10) * 50  # A cada 10 horas, aumenta 50 reais
        return mensalidade_base + acréscimo

    # Implementação do método emitirCertificado (da interface Certificavel)
    def emitirCertificado(self):
        return f"Certificado de Conclusão de {self.get_nome()} - Carga Horária: {self.get_cargaHoraria()} horas - Modalidade: {self.get_modalidade()}."
class Main:
    @staticmethod
    def main():
        # Criando uma instância da classe Curso
        curso1 = Curso("Curso de Python", "Avenida dos Programadores, 101", 120)

        # Exibindo as informações do curso
        print("Informações do Curso:")
        print(f"Nome: {curso1.get_nome()}")
        print(f"Endereço: {curso1.get_endereco()}")
        print(f"Carga Horária: {curso1.get_cargaHoraria()} horas")
        print(f"Mensalidade: R${curso1.calcularMensalidade()}")
        print(f"Certificado: {curso1.emitirCertificado()}\n")

        # Criando uma instância da classe CursoTecnico
        curso_tecnico = CursoTecnico("Curso Técnico em Redes", "Rua da Tecnologia, 200", 200, "Presencial")

        # Exibindo as informações do curso técnico
        print("Informações do Curso Técnico:")
        print(f"Nome: {curso_tecnico.get_nome()}")
        print(f"Endereço: {curso_tecnico.get_endereco()}")
        print(f"Carga Horária: {curso_tecnico.get_cargaHoraria()} horas")
        print(f"Modalidade: {curso_tecnico.get_modalidade()}")
        print(f"Mensalidade: R${curso_tecnico.calcularMensalidade()}")
        print(f"Certificado: {curso_tecnico.emitirCertificado()}")

# Chamando o método main
if _name_ == "_main_":
    Main.main()

10:class Curso(Escola, Certificavel):
    def _init_(self, nome, endereco, cargaHoraria):
        super()._init_(nome, endereco)
        self.__cargaHoraria = cargaHoraria

    def get_cargaHoraria(self):
        return self.__cargaHoraria

    def set_cargaHoraria(self, cargaHoraria):
        if cargaHoraria > 0:
            self.__cargaHoraria = cargaHoraria
        else:
            print("Erro: A carga horária deve ser maior que zero!")

    def calcularMensalidade(self):
        return 500  # Mensalidade padrão de 500 reais

    def emitirCertificado(self):
        return f"Certificado de conclusão de {self.get_nome()} - Carga Horária: {self.get_cargaHoraria()} horas."

    def exibirInformacoes(self):
        print(f"Nome: {self.get_nome()}")
        print(f"Endereço: {self.get_endereco()}")
        print(f"Carga Horária: {self.get_cargaHoraria()} horas")
        print(f"Mensalidade: R${self.calcularMensalidade()}")
        print(f"Certificado: {self.emitirCertificado()}\n")


class CursoTecnico(Curso):
    def _init_(self, nome, endereco, cargaHoraria, modalidade):
        super()._init_(nome, endereco, cargaHoraria)
        self.__modalidade = modalidade

    def get_modalidade(self):
        return self.__modalidade

    def set_modalidade(self, modalidade):
        self.__modalidade = modalidade

    def calcularMensalidade(self):
        mensalidade_base = super().calcularMensalidade()
        acréscimo = (self.get_cargaHoraria() // 10) * 50  # A cada 10 horas, aumenta 50 reais
        return mensalidade_base + acréscimo

    def emitirCertificado(self):
        return f"Certificado de Conclusão de {self.get_nome()} - Carga Horária: {self.get_cargaHoraria()} horas - Modalidade: {self.get_modalidade()}."

    def exibirInformacoes(self):
        print(f"Nome: {self.get_nome()}")
        print(f"Endereço: {self.get_endereco()}")
        print(f"Carga Horária: {self.get_cargaHoraria()} horas")
        print(f"Modalidade: {self.get_modalidade()}")
        print(f"Mensalidade: R${self.calcularMensalidade()}")
        print(f"Certificado: {self.emitirCertificado()}\n")
class Main:
    @staticmethod
    def main():
        # Criando uma lista de cursos (pode incluir tanto Curso quanto CursoTecnico)
        cursos = []

        # Adicionando instâncias de Curso e CursoTecnico na lista
        cursos.append(Curso("Curso de Python", "Avenida dos Programadores, 101", 120))
        cursos.append(CursoTecnico("Curso Técnico em Redes", "Rua da Tecnologia, 200", 200, "Presencial"))
        cursos.append(Curso("Curso de Java", "Rua dos Desenvolvedores, 202", 100))
        cursos.append(CursoTecnico("Curso Técnico em Eletrônica", "Avenida da Engenharia, 305", 150, "Online"))

        # Percorrendo a lista e chamando exibirInformacoes() de cada objeto
        for curso in cursos:
            curso.exibirInformacoes()


# Chamando o método main
if _name_ == "_main_":
    Main.main() 
