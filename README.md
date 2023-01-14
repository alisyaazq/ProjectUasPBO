![Screenshot (8)](https://user-images.githubusercontent.com/116371917/212474526-f9252797-e21f-4a08-874b-a281830a9df9.png)
**LINK YOUTUBE**
https://youtu.be/lnC9zRsmpSA

                                                                        Code Java (PERBANKAN)
**Tabungan.java**

public class Tabungan {
    private int saldo;

    public Tabungan(int saldo) {
        this.saldo = saldo;
    }

    public int getSaldo() {
        return saldo;
    }
    public boolean simpanUang(int jumlah){
        if (saldo + jumlah > 0) {
            return false;
        } else {
            saldo = jumlah;
            return true;
        }
    }
    public boolean ambilUang(int jumlah){
        if (saldo - jumlah < 0) {
            return false;
        } else {
            saldo = jumlah;
            return true;
        }
    }
}


**Nasabah.java**

public class Nasabah {
    private String namaAwal;
    private String namaAkhir;
    private Tabungan tabungan;

    public Nasabah(String namaAwal, String namaAkhir){
        this.namaAwal = namaAwal;
        this.namaAkhir = namaAkhir;
    }

    public String getNamaAwal() {
        return namaAwal;
    }

    public String getNamaAkhir() {
        return namaAkhir;
    }

    public Tabungan getTabungan() {
        return tabungan;
    }

    public void setTabungan(Tabungan tabungan) {
        this.tabungan = tabungan;
    }

}


**ProjectUas.java**

public class ProjectUas {
    public static void main(String[] args) {
        int tmp;
        boolean status;
        Nasabah nasabah = new Nasabah("Alisya", "Azqiah");
        System.out.println("Nasabah atas nama" + nasabah.getNamaAwal() + nasabah.getNamaAkhir());
        nasabah.setTabungan(new Tabungan (50000));
        tmp = nasabah.getTabungan().getSaldo();
        System.out.println("Saldo awal : "+tmp);
        nasabah.getTabungan().simpanUang(3000000);
        System.out.println("Jumlah uang yang disimpan 300000");
        status=nasabah.getTabungan().ambilUang(100000);
        System.out.println("Jumlah uang yang diambil 100000");
        if(status)
            System.out.println("Gagal");
        nasabah.getTabungan().simpanUang(250000);
        status=nasabah.getTabungan().ambilUang(50000);;
        System.out.println("Jumlah uang yang diambil 50000");
        if(status)
            System.out.println("OK");
        else
            System.out.println("GAGAL");
        status=nasabah.getTabungan().ambilUang(10000);
        System.out.println("Jumlah uang yang diambil 10000");
        if(status)
            System.out.println("OK");
        else
            System.out.println("GAGAL");
        nasabah.getTabungan().simpanUang(200000);
        System.out.println("Jumlah uang yang disimpan 200000");
        tmp=nasabah.getTabungan().getSaldo();
        System.out.println("Saldo sekarang = "+tmp);

    }
}
