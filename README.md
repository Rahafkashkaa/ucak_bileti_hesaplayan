 import java.util.Scanner;

 public class Main {

    public static void main(String[] args) {

  int km, ago, sec;
  double toplam,yasIndırımsızTutar, kmBasıUcret = 0.10;
  Scanner inp = new Scanner(System.in);

  System.out.print("Yaşınızı giriniz :");
  ago = inp.nextInt();

  System.out.print("Km bilgisi giriniz :");
  km = inp.nextInt();

  System.out.print("Tek yön için 1'i gidiş geliş için 2'yi tıklayın :");
  sec = inp.nextInt();


  if (km > 0 && ago > 0 && sec > 0 && sec < 3) {
      switch (sec) {
          case 1:
              if (ago < 12) {
                  toplam = km * kmBasıUcret * 0.50;
                  System.out.println("Toplam Tutarı :" + toplam);
              } else if (ago > 12 && ago < 24) {
                  toplam = km * kmBasıUcret * 0.10;
                  System.out.println("Toplam Tutarı :" + toplam);
              } else if (ago > 65) {
                  toplam = km * kmBasıUcret * 0.30;
                  System.out.println("Toplam Tutarı :" + toplam);

              }else { yasIndırımsızTutar=km*kmBasıUcret;
                  System.out.println("İndirimsiz Tutar :" + yasIndırımsızTutar);
              }
              break;
          case 2:
              if (ago < 12) {
                  toplam = km * kmBasıUcret * 0.50 * 0.20;
                  System.out.println("Toplam Tutarı :" + toplam);

              } else if (ago > 12 && ago < 24) {
                  toplam = km * kmBasıUcret * 0.10 * 0.20;
                  System.out.println("Toplam Tutarı :" + toplam);

              } else if (ago > 65) {
                  toplam = km * kmBasıUcret * 0.30 * 0.20;
                  System.out.println("Toplam Tutarı :" + toplam);

              }else { yasIndırımsızTutar=km*kmBasıUcret*0.20;
                  System.out.println("İndirimsiz Tutar :" + yasIndırımsızTutar);
              }
              break;
          default:


      }


  } else {
      System.out.println("Hatalı veri girdiniz !!!");
  }
 }
}
