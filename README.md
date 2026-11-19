# ============================================================
# Sistema Inteligente de Embarque em Aeroporto
# ============================================================

# -----------------------------
# Entrada de dados do passageiro
# -----------------------------

print("====================================")
print("SISTEMA INTELIGENTE DE EMBARQUE")
print("====================================")

nome = input("Nome: ")
idade = int(input("Idade: "))
nacionalidade = input("Nacionalidade: ")
destino = input("Destino: ")
numero_voo = input("Número do voo: ")

tipo_voo = input("Voo (Nacional/Internacional): ")

passaporte = input("Passaporte válido? (S/N): ")
visto = input("Visto válido? (S/N): ")
rg = input("Documento de identidade válido? (S/N): ")
bilhete = input("Bilhete emitido? (S/N): ")
checkin = input("Check-in realizado? (S/N): ")

bagagem_mao = input("Possui bagagem de mão? (S/N): ")
peso_mao = float(input("Peso da bagagem de mão (kg): "))

quantidade_malas = int(input("Quantidade de malas: "))
peso_despachada = float(input("Peso total bagagem despachada (kg): "))

animal = input("Possui animal de estimação? (S/N): ")
cadeirante = input("É cadeirante? (S/N): ")
gestante = input("É gestante? (S/N): ")
idoso = input("É idoso? (S/N): ")
menor = input("É menor desacompanhado? (S/N): ")

assistencia = input("Necessita assistência especial? (S/N): ")

material_perigoso = input("Transporta material perigoso? (S/N): ")
objetos_proibidos = input("Possui objetos proibidos? (S/N): ")
liquidos = input("Leva líquidos acima do permitido? (S/N): ")

chegou = input("Chegou com antecedência suficiente? (S/N): ")
portao = input("Está no portão correto? (S/N): ")
assento = input("Assento confirmado? (S/N): ")
prioritario = input("Tem embarque prioritário? (S/N): ")

seguro = input("Possui seguro viagem? (S/N): ")
autorizacao = input("Possui autorização para viagem? (S/N): ")
vacina = input("Vacinação obrigatória em dia? (S/N): ")
conexao = input("Possui conexão? (S/N): ")
embarcou_bagagem = input("Bagagem despachada corretamente? (S/N): ")

# -----------------------------
# Variáveis de controle
# -----------------------------

situacao = "Embarque Autorizado"
motivo = "Todos os requisitos atendidos."

# ======================================================
# Verificações
# ======================================================

# 1
if bilhete == "N":
    situacao = "Embarque Recusado"
    motivo = "Bilhete não emitido."

# 2
if checkin == "N":
    situacao = "Encaminhar ao balcão da companhia aérea"
    motivo = "Check-in não realizado."

# 3
if rg == "N":
    situacao = "Embarque Recusado"
    motivo = "Documento inválido."

# 4
if tipo_voo == "Internacional" and passaporte == "N":
    situacao = "Embarque Recusado"
    motivo = "Passaporte inválido."

# 5
if tipo_voo == "Internacional" and visto == "N":
    situacao = "Embarque Recusado"
    motivo = "Visto inexistente."

# 6
if tipo_voo == "Internacional" and seguro == "N":
    situacao = "Encaminhar ao balcão da companhia aérea"
    motivo = "Seguro viagem não apresentado."

# 7
if tipo_voo == "Internacional" and vacina == "N":
    situacao = "Embarque Recusado"
    motivo = "Vacinação obrigatória ausente."

# 8
if objetos_proibidos == "S":
    situacao = "Embarque Recusado"
    motivo = "Objetos proibidos encontrados."

# 9
if material_perigoso == "S":
    situacao = "Embarque Recusado"
    motivo = "Material perigoso."

# 10
if liquidos == "S":
    situacao = "Embarque Autorizado com Restrições"
    motivo = "Necessária retirada dos líquidos."

# 11
if peso_mao > 10:
    situacao = "Cobrança de Excesso de Bagagem"
    motivo = "Bagagem de mão acima do permitido."

# 12
if peso_despachada > 23:
    situacao = "Cobrança de Excesso de Bagagem"
    motivo = "Bagagem despachada acima do limite."

# 13
if quantidade_malas > 2:
    situacao = "Cobrança de Excesso de Bagagem"
    motivo = "Quantidade de malas excedida."

# 14
if menor == "S" and autorizacao == "N":
    situacao = "Embarque Recusado"
    motivo = "Menor desacompanhado sem autorização."

# 15
if cadeirante == "S":
    situacao = "Necessário Atendimento Especial"
    motivo = "Passageiro cadeirante."

# 16
if gestante == "S":
    situacao = "Necessário Atendimento Especial"
    motivo = "Gestante."

# 17
if idoso == "S":
    situacao = "Necessário Atendimento Especial"
    motivo = "Idoso."

# 18
if assistencia == "S":
    situacao = "Necessário Atendimento Especial"
    motivo = "Assistência especial."

# 19
if prioritario == "S":
    print("Embarque prioritário autorizado.")

# 20
if chegou == "N":
    situacao = "Encaminhar ao balcão da companhia aérea"
    motivo = "Passageiro atrasado."

# 21
if portao == "N":
    situacao = "Encaminhar ao balcão da companhia aérea"
    motivo = "Portão incorreto."

# 22
if assento == "N":
    situacao = "Encaminhar ao balcão da companhia aérea"
    motivo = "Assento não confirmado."

# 23
if embarcou_bagagem == "N":
    situacao = "Encaminhar ao balcão da companhia aérea"
    motivo = "Bagagem não despachada."

# 24
if animal == "S":
    print("Verificar documentação do animal.")

# 25
if idade < 2:
    print("Passageiro bebê.")

# 26
if idade >= 60:
    print("Possui prioridade.")

# 27
if idade >= 18 and idade < 60:
    print("Passageiro adulto.")

# 28
if idade < 18:
    print("Passageiro menor de idade.")

# 29
if tipo_voo == "Nacional":
    print("Voo nacional confirmado.")

# 30
if tipo_voo == "Internacional":
    print("Voo internacional confirmado.")

# 31
if bagagem_mao == "S":
    print("Bagagem de mão registrada.")

# 32
if bagagem_mao == "N":
    print("Sem bagagem de mão.")

# 33
if conexao == "S":
    print("Passageiro possui conexão.")

# 34
if conexao == "N":
    print("Sem conexão.")

# 35
if nacionalidade == "Brasileira":
    print("Passageiro brasileiro.")

# 36
if nacionalidade != "Brasileira":
    print("Passageiro estrangeiro.")

# 37
if passaporte == "S":
    print("Passaporte válido.")

# 38
if passaporte == "N":
    print("Passaporte inválido.")

# 39
if visto == "S":
    print("Visto válido.")

# 40
if visto == "N":
    print("Visto ausente.")

# 41
if seguro == "S":
    print("Seguro viagem confirmado.")

# 42
if seguro == "N":
    print("Sem seguro viagem.")

# 43
if autorizacao == "S":
    print("Autorização apresentada.")

# 44
if autorizacao == "N":
    print("Sem autorização.")

# 45
if vacina == "S":
    print("Vacinação em dia.")

# 46
if vacina == "N":
    print("Vacinação pendente.")

# 47
if material_perigoso == "N":
    print("Sem material perigoso.")

# 48
if objetos_proibidos == "N":
    print("Nenhum objeto proibido.")

# 49
if liquidos == "N":
    print("Líquidos dentro do permitido.")

# 50
if quantidade_malas == 0:
    print("Sem bagagem despachada.")

# 51
if quantidade_malas == 1:
    print("Uma mala despachada.")

# 52
if quantidade_malas == 2:
    print("Duas malas despachadas.")

# 53
if peso_mao <= 10 and bagagem_mao == "S":
    print("Peso da bagagem de mão permitido.")

# 54
if peso_despachada <= 23 and quantidade_malas > 0:
    print("Bagagem despachada dentro do limite.")

# 55
if chegou == "S" and checkin == "S":
    print("Chegada dentro do horário.")

# 56
if rg == "S" and bilhete == "S":
    print("Documentação básica correta.")

# 57
if tipo_voo == "Internacional" and passaporte == "S" and visto == "S":
    print("Documentação internacional correta.")

# 58
if prioridade == "S" if False else False:
    pass

# 59
if idade >= 80:
    print("Prioridade máxima.")

# 60
if situacao == "Embarque Autorizado":
    print("Todos os requisitos atendidos.")

# ======================================================
# Resultado Final
# ======================================================

print("\n==============================")
print("RESUMO DO EMBARQUE")
print("==============================")

print("Nome:", nome)
print("Destino:", destino)
print("Número do voo:", numero_voo)
print("Situação:", situacao)
print("Motivo:", motivo)

print("\nOrientações:")

if situacao == "Embarque Autorizado":
    print("Dirija-se ao portão de embarque.")

elif situacao == "Embarque Autorizado com Restrições":
    print("Regularize a restrição antes do embarque.")

elif situacao == "Cobrança de Excesso de Bagagem":
    print("Efetue o pagamento do excesso de bagagem.")

elif situacao == "Necessário Atendimento Especial":
    print("Procure o balcão de atendimento especial.")

elif situacao == "Encaminhar ao balcão da companhia aérea":
    print("Dirija-se ao balcão para regularização.")

else:
    print("Embarque recusado. Procure a companhia aérea.")
