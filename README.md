# ElectBillGen
package electBillGeneration;

import java.util.Scanner;

public class ElectBillGeneration {
int consumerNo;
String consumerName;
int PrevReading;
int CurrReading;
String EBConn;
double Bill;
void input_data()
{
	Scanner sc=new Scanner(System.in);
	System.out.println("\n enter consumer number:");
	consumerNo=sc.nextInt();
	System.out.println("\n enter consumer name:");
	consumerName=sc.next();
	System.out.println("\n enter previous units:");
	PrevReading=sc.nextInt();
	System.out.println("\n enter current unit consumed:");
	CurrReading=sc.nextInt();
	System.out.println("enter the types of EB connection(domestic or commercial)");
	EBConn =sc.next();
	
	
	
}
double calculate_bill()
{
	int choice;
	if(EBConn=="domestic")
		choice=1;
	else
		choice=2;
	switch(choice)
	{
	case 1:
		if(CurrReading >=0 && CurrReading <=100)
			Bill=CurrReading*1;
		else if(CurrReading >100 && CurrReading<=200)
			Bill=(100*1)+((CurrReading-100)*2.50);
		else if(CurrReading>200 && CurrReading<=500)
			Bill=(100*1)+(100*2.50)+((CurrReading-200)*4);
		else
			Bill=(100*1)+(100*2.50)+(300*4)+((CurrReading-500)*6);
		break;
	case 2:
		if(CurrReading>=0 && CurrReading <=100)
			Bill=CurrReading*2;
		else if(CurrReading>100 && CurrReading <=200)
			Bill=(100*1)+((CurrReading-100)*4.50);
		else if (CurrReading > 200 && CurrReading <=500)
			Bill=(100*1)+(100*2.50)+((CurrReading-200)*6);
		else
			Bill=(100*1)+(100*2.50)+(300*4)+((CurrReading-500)*7);
		break;
			
	}
	return Bill;
}
void display()
{
	System.out.println("-------------------------");
	System.out.println("ELECTRICITY BILL");
	System.out.println("--------------------------");
	System.out.println("Consumer number:"+consumerNo);
	System.out.println("Consumer name:"+consumerName);
	System.out.println("Consumer previous units:"+PrevReading);
	System.out.println("Consumer current units:"+PrevReading);
	System.out.println("Consumer current units:"+CurrReading);
	System.out.println("type of EBConnection:"+EBConn);
	System.out.println("----------------------------");
	System.out.println("total amount(rs):"+Bill);
	
	
}

}
class ElectBillGen
{
	public static void main(String[]args)
	{
		ElectBillGeneration b=new ElectBillGeneration();
		b.input_data();
		b.calculate_bill();
		b.display();
	}
}
