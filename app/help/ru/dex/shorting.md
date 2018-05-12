# Короткая продажа BitAssets

Для увеличения Вашего воздействия на BTS и увеличения ликвидности активов BitAssets, таких как USD, EUR, GOLD и др., Вы можете *занять* этот актив bitAsset у сети и *выставить шорт*. Здесь мы кратко опишем данную процедуру.

## Заём

Сеть BitShares способна создавать любое количество каждого актива BitAsset и занимать его субьектам экосистемы при условии предоставления достаточного залога.

- *расчетная цена*: Цена за 1 BTS взятая с внешних бирж.
- *уровень обеспечивающего залога* (MCR): Размер залога, определённый участниками рынка как минимальный
- *максимальный размер сжатия шорта* (MSQR): Установленный участниками рынка размер вынужденной покупки актива медведями по высокому курсу из опасения еще большего его роста
- *защита от сжатия шорта*(SQP): Определяет предельную величину принудительного покрытия позиции 
- *черта марджин колла* (CP): Цена, при которой шорт будет принудительно закрыт

### Маржин Колл

Сеть BitShares способна применять маржин колл к тем позициям, которые не имеют достаточного залогового обеспечения для покрытия одолженных ими bitAssets. Маржин колл будет происходить каждый раз, когда самая высокая ставка окажется меньше, чем *цена досрочного выкупа* и больше *SQP*. Маржинальная позиция будет вынуждена продавать своё залоговое обеспечение каждый раз, когда самое высокое предложение на покупку обеспечения окажется меньше, чем цена дострочного выкупа (x/BTS).

    SQP = расчетная цена / MSQR
    цена дострочного выкупа = DEBT / COLLATERAL * MCR
    

The margin call will take the collateral, buy shares of borrowed bitAsset at market rates up to the SQP and close the position. The remaining BTS of the collateral are returned to the customer.

### Settlement

Holders of any bitAsset can request a settlement at a *fair price* at any time. The settlement closes the borrow/short positions with lowest collateral ratio and sells the collateral for the settlement.

## Selling

After borrowing bitAssets, they can be sold free at any of the corresponding markets at any price a buyer is willing to pay. With this step, the short-selling is now complete and you are short that particular bitAsset.

## Updating Collateral Ratio

At any time, the holder of a borrow/short position can modify the collateral ratio in order to flexibly adjust to market behavior. If the collateral ratio is increase, an additional amount of BTS is locked as collateral, while reducing the collateral ratio will require an amount of the corresponding BitAsset to be payed back to the network.

## Covering

To close a borrow/short position, one must hold the borrowed amount of that particular bitAsset to hand it over to the BitShares network. After that, the BitAssets are reduced from the corresponding supply and the collateral is released and given back to its owner.