# Algoritma Checkout Tokopedia

## Deskriptif
1. Start
2. Pilihlah barang yang akan di checkout
3. Masukan barang yang akan di checkout kedalam keranjang
4. Lakukan lah pembayaran terhadap barang yang akan di checkout
5. Jika pembayaran sudah dilakukan maka cart akan kosong dan muncul status sudah dibayar
6. Jika pembayaran tidak dilakukan maka akan muncul status belum dibayar
7. Finish

## Flowchart

```mermaid
flowchart TD
idStart(("Start"))
idInput[/"Input: Product"/]
idCart["Cart += Product"]
kondisiBayar{"isPaid?"}
kondisiBayarFalse[/"Output: #quot;Belum Dibayar#quot;"/]
kondisiBayarTrue[/"Output: #quot;Sudah Dibayar#quot;"/]
statusCart["Cart = null"]
idStop((("Stop")))

idStart --> idInput --> idCart --> kondisiBayar

kondisiBayar -- False --> kondisiBayarFalse
kondisiBayarFalse --> kondisiBayar
kondisiBayar -- True --> statusCart
statusCart --> kondisiBayarTrue --> idStop

```