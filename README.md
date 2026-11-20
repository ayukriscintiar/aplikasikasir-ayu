package aplikasikasir;

import java.util.ArrayList;
import java.util.List;

public class Transaksi {
    private List<ItemTransaksi> items = new ArrayList<>();

    public void tambah(Barang barang, int qty) { items.add(new ItemTransaksi(barang, qty)); }
    public void hapus(int index) { if(index >= 0 && index < items.size()) items.remove(index); }
    public void clear() { items.clear(); }
    public List<ItemTransaksi> getItems() { return items; }

    public double getTotal() {
        double total = 0;
        for (ItemTransaksi it : items) total += it.getSubtotal();
        return total;
    }
}
