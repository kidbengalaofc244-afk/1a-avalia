def sistema_escolar():
    notas = []
    print("=== Sistema Escolar ===")
    
    # Coleta das 9 notas
    for i in range(1, 10):
        while True:
            try:
                nota = float(input(f"Digite a nota {i} (0 a 100): "))
                if 0 <= nota <= 100:
                    notas.append(nota)
                    break
                else:
                    print("❌ A nota deve estar entre 0 e 100.")
            except ValueError:
                print("❌ Digite um número válido.")
    
    # Divide as notas em trimestres
    trimestre1 = notas[0:3]
    trimestre2 = notas[3:6]
    trimestre3 = notas[6:9]
    
    # Calcula médias
    media_t1 = sum(trimestre1) / 3
    media_t2 = sum(trimestre2) / 3
    media_t3 = sum(trimestre3) / 3
    media_final = (media_t1 + media_t2 + media_t3) / 3
    
    # Exibe resultados
    print("\n=== Resultados ===")
    print(f"Média do 1º trimestre: {media_t1:.2f}")
    print(f"Média do 2º trimestre: {media_t2:.2f}")
    print(f"Média do 3º trimestre: {media_t3:.2f}")
    print(f"Média final anual: {media_final:.2f}")
    
    # Situação final
    if media_final >= 48:
        print("✅ Situação: APROVADO")
    elif media_final >= 40:
        print("⚠️ Situação: RECUPERAÇÃO")
    else:
        print("❌ Situação: REPROVADO")

# Executa o sistema
sistema_escolar()
