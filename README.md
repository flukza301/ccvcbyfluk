<! DOCTYPE html>
< html  lang = " en " >
< head >
< meta  name = ' viewport '  content = ' initial-scale = 1, minimum-scale = 1, maximum-scale = 1 ' />
< meta  http-equiv = "เนื้อหาเนื้อหาประเภท"  content = " text / html; charset = utf-8 " />
< meta  http-equiv = " x-ua-compatible "  content = " IE = 10 " >
< title > </ title >
< สไตล์ ประเภท = "ข้อความ css / " > #initialLoading { พื้นหลัง : URL ( สินทรัพย์ / htmlimages / loader.gif ) ไม่มีซ้ำ ศูนย์ ศูนย์ ; สีพื้นหลัง : #ffffff ; ตำแหน่ง : แน่นอน ; margin : auto ; ด้านบน : 0 ; ซ้าย : 0 ; ขวา : 0 ; ด้านล่าง : 0 ; z-index :10010 ;} </ style >

< script >
var deviceReady =  false ;
var initCalled =  false ;
var initialized =  false ;
ฟังก์ชั่น onBodyLoad ()
{
	if ( typeof  window . device  ===  ' undefined ' )
	{
		เอกสาร addEventListener ( " deviceready " , onDeviceReady, false );
	}
	อื่น
	{
		onDeviceReady ();
	}
}
ฟังก์ชัน onDeviceReady ()
{
	deviceReady =  true ;
	ถ้า (initCalled ===  จริง )
		initializeCP ();
}
ฟังก์ชัน initializeCP ()
{
	ถ้า (เริ่มต้น)
		กลับ ;
	initCalled =  true ;
	ถ้า ( cp . pg  && deviceReady ===  false )
		กลับ ;
	ฟังก์ชัน cpInit ()
	{
		document.body.innerHTML = "<div class = 'cpMainContainer' id = 'cpDocument' style = 'left: 0px; top: 0px;' > <div id = 'main_container' style = 'top: 0px; position: absolute; width: 100% height; 100%;'> <div id = 'projectBorder' style = 'top: 0px; left: 0px; width : 100% ความสูง: 100% ตำแหน่ง: absolute แสดง: block '> </ div> <div class =' ​​shadow 'id =' project_container 'style =' left: 0px; top: 0px; width: 100%; ความสูง: 100%; position: absolute; ล้น: ซ่อน' > <div id = 'project' class = 'cp-movie' style = 'width: 100%; height: 100%; overflow: hidden;'> <div id = 'project_main' class = 'cp-timeline cp-main '> <div id =' div_Slide 'onclick =' cp.handleClick (event) 'style =' top: 0px; width: 100% height; 100%; div id = 'playbar' style = 'bottom: 0px; ตำแหน่ง: คงที่>> </ div> <div id = 'cc' style = 'left: 0px; ตำแหน่ง: ถาวร visibility: hidden; ชี้เหตุการณ์: none;' onclick = 'cp.handleCCClick (event)'> <div id = 'ccText' style = 'left: 0px; float: left; position: absolute; width: 100% height; 100%;'> <p style = ' ขอบด้านขวา: 8px; margin-top: 2px; '> </ p> </ div> <div id =' ccClose 'style =' background-image: url (./ assets / htmlimages / ccClose.png); ขวา: 10px; position: absolute; เคอร์เซอร์: ตัวชี้ความกว้าง: 13px; ความสูง: 11px;' / div> <div id = 'gestureIcon' class = 'gestureIcon'> </ div> <div id = 'gestureHint' class = 'gestureHintDiv'> <div id = 'gImage'
		ซีพี DoCPInit ();
		var lCpExit =  หน้าต่าง [ " DoCPExit " ];
		หน้าต่าง [ " DoCPExit " ] =  ฟังก์ชัน ()
		{
			ถ้า ( ซีพี . UnloadActivties )
				ซีพี UnloadActivties ();
			lCpExit ();
		};
	}
	
	cpInit ();
	initialized =  true ;
}
</ script >

</ head >
< body  onload = " onBodyLoad () " >
		< div  id = ' initialLoading ' > </ div >
< script >
		( ฟังก์ชัน ()
		{
			ถ้า ( เอกสาร . documentMode  <  9 )
			{
				เอกสาร ร่างกาย innerHTML  =  " " ;
				เอกสาร เขียน ( "เนื้อหาที่คุณพยายามจะดูไม่ได้รับการสนับสนุนในโหมดเอกสารปัจจุบันของ Internet Explorer เปลี่ยนโหมดเอกสารไปเป็นมาตรฐานของ Internet Explorer 9 และลองดูเนื้อหาอีกครั้ง <br> เมื่อต้องการเปลี่ยนโหมดเอกสารกด F12 , คลิก Document Mode: <current mode> จากนั้นเลือก Internet Explorer 9 Standards " );
				กลับ ;
			}
			หน้าต่าง addEventListener ( " load " , function ()
			{
				setTimeout ( ฟังก์ชัน ()
				{					
					varสคริปต์= เอกสาร createElement ( ' script ' );
					ต้นฉบับ type  =  ' text / javascript ' ;
					ต้นฉบับ src  =  ' asset / js / CPXHRLoader.js ' ;
					ต้นฉบับ defer  =  'เลื่อน' ;
					ต้นฉบับ onload  =  function ()
					{
						var lCSSLoaded =  false ;
						var lJSLoaded =  false ;
						 สร้างฟังก์ชันDIVs ()
						{
							if (lCSSLoaded && lJSLoaded)
							{
								initializeCP ();
							}
						}
						cpXHRJSLoader css ( ' asset / css / CPLibraryAll.css ' , function () {
							lCSSLoaded =  true ;
							construDIVs ();
						});
						var lJSFiles = [   ' asset / js / jquery-1.6.1.min.js ' , 'สินทรัพย์ / js / CPM.js ' , 'สินทรัพย์ / playbar / playbarScript.js ' ];
						cpXHRJSLoader js (lJSFiles ฟังก์ชัน ()
						{
							// console.log ("js loaded");
							lJSLoaded =  true ;
							construDIVs ();
						});
					}
					เอกสาร getElementsByTagName ( ' head ' ) [ 0 ] appendChild (สคริปต์);
				}, 1 );
			}, เท็จ );
		}) ();
		
</ script >
< noscript  style = " text-align : center ; font-size : 24 px ; " > เปิดการใช้งาน Javascript ในเบราว์เซอร์ </ noscript >
</ body >
</ html >
