# analise_hotel_booking

- **Descrição**:Este é um projeto de análise de dados utilizando SQL, realizando uma análise exploratória de dados e compartilhando os insights obtidos através da base de dados *hotel booking demand* otida através do Kaggle.
- **Objetivos**: Analisar as reservas realizadas entre Julho de 2015 e Agosto de 2017 para responder perguntas de negócios relevantes e encontrar pontos a serem explorados em cada tipo de hotel analisado com a finalidade de aumentar os lucros da empresa.
- **Resultados**: 

## Descrição da Tabela
- ADR(Numérico): Tarifa média, valor de todas as transações de hospedagem dividido pelo número total de noites de estadia.
- Adults(Inteiro): Número de adultos na reserva.
- Agent(Categórica): ID da agência de viagens que fez a reserva.
- ArrivalDateDayOfMonth(Inteiro): Dia do mês da data de chegada.
- ArrivalDateMonth(Categórica): Mês da data de chegada, com 12 categorias("janeiro" a "Dezembro).
- ArrivalDateWeekNumber(Inteiro): Número da semana da data de chegada
- ArrivalDateYear(Inteiro): Ano da data de chegada.
- AssignedRoomType(Categórica): Código do tipo de quarto atribuído à reserva. O tipo atribuído pode ser diferente do reservado por questões operacionais ou a pedido do cliente. o Código vai de A até I, K, L e P.
- Babies(Inteiro): Número de bebês na reseva.
- BookingChanges(Inteiro): Número de alterações feitas na reserva desde a entreada no sistema até o check-in ou cancelamento.
- Children(Inteiro): Número de crianças na reserva, incluindo pagantes e não pagantes.
- Company(Categórica): ID da empresa responsável por fazer ou pagar a reserva.
- Country(Categórica): País de origem do cliente, representado no formato ISO 3155-3:2013.
- CustomerType(Categórica): Tipo de cliente, com quatro categorias diferentes:
    - Contract: Reserva associada a uma alocação ou outro tipo de contrato associado a ela.
    - Group: Reserva associada a um grupo.
    - Transient: Reserva individual, não associada a grupo ou contrato.
    - Transient-party: Reserva individual, mas associada a outras reservas individuais.
- DaysInWaitingList(Inteiro): Número de dias que a reserva permaneceu na lista de espera antes de ser confirmada.
- DepositType(Categórica): Tipo de deposito feito pelo cliente para garantir a reserva, com três categorias:
    - No Deposit: Nenhum depósito foi feito.
    - Non Refund: Depósito foi feito no valor total da estadia, não reembonsável.
    - Refundable: Depósito foi feito, mas abaixo do valor total da estadia, sendo reembolsável.
- DistribuitionChannel(Categórica): Canal de distribuição da reserva:
    - Corporate: -
    - Direct: -
    - GDS: -
    - TA/TO: "TA" - Agentes de viagens. "TO" - Operadores de turismo.
    - Undefined: Não informado.
- Hotel(Categórica): City Hotel ou Resort Hotel
- IsCanceled(Categórica): Reverva Cancelada (1). Reserva não cancelada (0).
- IsRepeatedGuest(Categórica): Hóspede repitido (1). Hóspede não repetido (0).
- LeadTime(Inteiro): Número de dias entre a data de inserção da reserva no sistema e a data de chegada.
- MarketSegment(Categórica): Segmento de mercado da reserva:
    - Aviation: -
    - Complementary: -
    - Corporate: -
    - Direct: -
    - Groups: -
    - Offline TA/TO: - "TA" - Agentes de viagens. "TO" - Operadores de turismo.
    - Offline TA: - "TA" - Agentes de viagens.
    - Undefined: Não definido.
- Meal(Categórica): Tipo de refeição reservada:
    - SC: Sem refeição.
    - BB: Café da manhã.
    - HB: Meia pensão (café da manhã e mais uma refeição, geralmente o jantar).
    - FB: Pensão completa (café da manhã, almoço e jantar).
- PreviousBookingsNotCanceled(Inteiro): Número de reservas anteriores que não foram canceladas pelo cliente.
- PreviousCancellations(Inteiro): Número de reservas anteriores canceladas pelo cliente.
- RequiredCardParkingSpaces(Inteiro): Número de vagas de estacionamento requeridas pelo cliente.
- ReservationStatus(Categórica): Último status da reserva, com três categorias:
    - Canceled: Reserva cancelada.
    - Check-Out: Cliente fez check-in, mas já fez check-out.
    - No-Show: Cliente não compareceu e não avisou o motivo.
- ReservationStatusDate(Data): Data em que o último status da reserva foi atualizado.
- ReservedRoomType(Categórica): Código do tipo de quarto reservado. Indo de A a H, L e P.
- StaysInWeekendNights(Inteiro): Número de noites de fim de semana (sábado ou domingo) incluídas na reserva.
- StaysInweekNights(Inteiro): Número de noites de semana (segunda a sexta) incluídas na reserva.
- TotalOfSpecialRequests(Inteiro): Número total de pedidos especiais feitos pelo cliente (ex: cama de solteiro, andar alto).

## Resultados encontrados:
O total de reservas realizadas no hotel da cidade representa um total de 66,45% da base de dados, enquanto o hotel resort corresponde a 33,55%. Devemos nos atentar a uma diferença no lucro que será explorada mais a frente.

![Total Reservas](./assets/reserva.png)

Na imagem abaixo podemos ver o percentual relativo de reservas válidas e canceladas. O hotel na cidade tem um total de 41,73% das reservas canceladas, já o hotel resort tem apenas 27,76% das reservas canceladas. 
![Percentual Reservas](./assets/percentual_reservas.png)

Mesmo com um grande número de reservas canceladas, o hotel na cidade ainda conta com 61,5% de reservas válidas em relação ao total com o hotel resort.

O gráfico abaixo mostra o total de hospedagens durante a linha de tempo documentada. Existem pontos a serem levados em consideração nos dois tipos de hotel:
- Hotel na Cidade:
  - Os dados oscilam durante dos meses, podemos ver que no primeiro mês tiveram menos de 500 hospedagens, tendo uma alta de 1986 hospedagens no mês de setembro, seguido por outra queda no mês de novembro, chegando a ter apenas 934 hospedagens, voltando a ter um pico entre os meses de março e abril. Podemos ver esse padrão se repetindo novamente em 2016 onde houve uma queda nas hospedagens no mês de novembro  com um pico após o mês de março.
- Hotel Resort:
  - Diferente do hotel na cidade, o hotel resort não tem uma oscilação com picos significativos durante os meses apresentados.
  - Podemos ver dois meses com mais reservas que os demais, ambos ocorreram no ano de 2016, atingindo a marca de pouco mais de 1400 hospedagens. Esse evento ocorreu nos meses de março e outubro.
  - A maior baixa observada ocorreu no mês de Janeiro de 2016, mas não ocorreu novamente durante os meses seguintes.
        
![Total Reservas por Mês](./assets/hospedagem_hotel.png)

Uma análise na média gasta por hóspede mostra uma tendência diferente nos dois hotéis:
- Hotel na Cidade:
    - Os meses de Outubro a Março mostram um gasto médio por hóspede de aproximadamente 21,99% menor que nos demais meses.
    - Os meses de agosto/setembro e maio mostram um gasto médio de aproximadamente 19,60% maior que nos demais meses.
    - Diferente do total de hospedagem, o gasto médio por hóspede no hotel da cidade não apresenta uma mudança significativa ao decorrer dos meses.
- Hotel Resort:
    - Apresenta picos acentuados nos meses de julho, agosto e setembro, com sua alta sendo sempre em agosto. Esse evento acontece durante as férias de verão na região.
    - Os meses de Julho, Agosto e Dezembro tem um gasto médio por cliente de 118,91% maior que os outros meses.
    - Somente o mês de agosto tem um gasto médio por cliente de 125,95% maior que os outros meses.
    - O mês de dezembro (ano novo) apresenta uma alta de 40,99% em comparação com seus meses vizinhos (novembro e janeiro).
    - Enquanto as hospedagens no hotel resort não tem picos muito acentuados, o gasto médio por hóspede tem variações significativas para diferentes épocas do ano, como apontado nas férias de verão e ano novo.
 
![Gasto médio em cada hospedagem por Mês](./assets/media_gasto_hospedagem.png)

Análise do total gerado

## Dataset
- Dataset coletado no Kaggle.
- Link: https://www.kaggle.com/datasets/jessemostipak/hotel-booking-demand
## Contato
- Linkedin: https://www.linkedin.com/in/gabrielhlenz/
- Github: https://github.com/GabrielhLenz
- Email: gabrielxlenz@gmail.com
