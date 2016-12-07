# ReadDataExcel
Reading data from Excel using Selenium Webdriver
public class ReadDataExl {

	@Test
	public void ReadData(){
		File src=new File("C:/Users/Khushi/Downloads/Selenium/TestCaseData.xls");
		try {
		Workbook wb=Workbook.getWorkbook(src);
		Sheet sh1=wb.getSheet(0);
		
		int intRow = sh1.getRows();
		int intCol = sh1.getColumns();
		
		for (int row=1; row<intRow; row++) {
			for (int col=0; col<intCol; col++) {
				System.out.print(sh1.getCell(col, row).getContents() + "\t");
			}
			System.out.println();
		}
		wb.close();
	}
		catch (BiffException e){
			e.printStackTrace();
		}
		catch (IOException e)
		{	e.printStackTrace();
		}
	
	}
	
}
