# Capgemini

package calculadora;

import java.text.ParseException;
import java.text.SimpleDateFormat;
import java.util.Calendar;
import java.util.Scanner;
import java.util.Date;
import java.util.logging.Level;
import java.util.logging.Logger;

public class Calculadora {

   
    Caracteristicas anuncio = new Caracteristicas();
    
    public static void main(String[] args) throws ParseException {
        Scanner sc = new Scanner (System.in);
        Caracteristicas anuncio = new Caracteristicas();
       SimpleDateFormat sdf = new  SimpleDateFormat("dd/MM/yyyy");
        Calendar cal = Calendar.getInstance();
       
        
        double valor_total;
        double qtd_pessoas_final =0;
        double qtd_pessoas_anunciooriginal=0;
        double click_cada100=0;
        double compartilhar_anuncios_cadaclique=0;
        double novas_vizualizações=0;
        
        double click_cada1002=0;
        double compartilhar_anuncios_cadaclique2=0;
        double novas_vizualizações2=0;
        
        int i;
        double rec;
        double tot=0;
        
        
        
/*----------------------------------------1° Parte CALCULADORA DE ANÚNCIOS-----------------------------------------------*/

        System.out.println("Digite o valor que será investido para os anúncios");
        valor_total = sc.nextDouble();
          
          qtd_pessoas_anunciooriginal = (30*valor_total);
          click_cada100 = (qtd_pessoas_anunciooriginal/100)*12;
          compartilhar_anuncios_cadaclique = (click_cada100/20)*3;
          novas_vizualizações = compartilhar_anuncios_cadaclique*40;
          
          
          tot = novas_vizualizações;
          rec = novas_vizualizações;
         
          for(i=0;i<2;i++)
          {
              
              
          click_cada1002 = (rec/100)*12;
          compartilhar_anuncios_cadaclique2 = (click_cada1002/20)*3;
          novas_vizualizações2 = compartilhar_anuncios_cadaclique2*40;
          rec=novas_vizualizações2;
          tot += novas_vizualizações2;
            
          }
          
          double finall = tot+ qtd_pessoas_anunciooriginal;
          System.out.println("Quantidade aproximada da pessoas que viram o anúncio: "+Math.round(finall));
       
          
 /*----------------------------------------2° Parte CADASTRO DOS ANÚNCIOS-----------------------------------------------*/
          
           System.out.println("Digite o nome do anúncio");
        anuncio.nome = sc.nextLine();sc.next();
        
        System.out.println("Digite o nome do cliente");
        anuncio.Cliente = sc.nextLine();sc.next();
       
     
        
        System.out.println("Digite a data de inicio ");
        anuncio.datainicio = sdf.parse(sc.next());
        cal.setTime(anuncio.datainicio);
        int datinicio = cal.get(Calendar.DAY_OF_YEAR);
        
        
        System.out.println("Digite a data de termino ");
         anuncio.datatermino = sdf.parse(sc.next());
        cal.setTime(anuncio.datatermino);
        int dattermino = cal.get(Calendar.DAY_OF_YEAR);       
        int diferenca_dia = dattermino - datinicio ;
        
        
        
        double max;
        double maxclique=0;
        double maxvizu=0;
        max = novas_vizualizações;
        
        for(i=0;i<4;i++)
          {
              
              
          click_cada1002 = (rec/100)*12;
          compartilhar_anuncios_cadaclique2 = (click_cada1002/20)*3;
          novas_vizualizações2 = compartilhar_anuncios_cadaclique2*40;
          rec=novas_vizualizações2;
          max += novas_vizualizações2;
          maxclique += click_cada1002; 
          maxvizu += compartilhar_anuncios_cadaclique2;
          }
        
        
       
        
        
        System.out.println("Digite qual será o investimento por dia");
        anuncio.investimento_dia = sc.nextDouble();
        
        
        
        
        System.out.println("Relatório: ");
        System.out.print("\n");
         
        System.out.println("Valor total investido: "+diferenca_dia*anuncio.investimento_dia);
        System.out.println("Máximo de cliques: "+Math.round(maxclique));
           
        finall = 0;
        finall = max+qtd_pessoas_anunciooriginal;
        System.out.println("Quantidade máxima de vizualizações: "+Math.round(finall));
        System.out.println("Quantidade máxima de compartilhamentos: " +Math.round(maxvizu));
          
          
         
    }
    
}
