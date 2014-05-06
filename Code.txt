<html>
	<head>
		
	</head>
	<style>
		Body{
			background-image:url("media/background.png");
		}
		#stats_main{
			width:350px;
			height:450px;
			background-color:rgba(255,255,255,1);
			margin-top:50px;
			padding:15px;
			border-radius:20px;
		}
		#stats_main_inner{
			border-radius:20px;
			width:100%;
			height:100%;
			background-color:rgba(255,255,255,1);
			border:thin dashed gray;
		}
		.stats_main_inner_header{
			border-bottom:thin dotted gray;
			height:50px;
			line-height:50px;
			font-size:25px;
			font-family:'Trebuchet MS';
			color:dimgray;
			width:90%;
		}
		.stats_main_inner_table{
			width:100%;
			
			margin-top:30px;
		}
		.stats_main_inner_table tr{
			height:40px;
		}
		.stats_main_inner_type{
			width:55%;
			font-size:16px;
			font-family:'Trebuchet MS';
			text-align:right;
			padding-right:15px;
		}
		.stats_main_inner_icon{
			width:20px;
			height:20px;
			float:left;
		}
		.stats_main_inner_status{
			width:45%;
			padding-left:15px;
			text-align:left;
		}
	</style>
	<body>
		<?php
			$pingworked['80'] = false;
			
			$host = '87.106.52.58';
			
			$port = 80;
			$waitTimeoutInSeconds = 1;
			if ($fp = fsockopen($host,$port,$errCode,$errStr,$waitTimeoutInSeconds)) {
			  $pingworked['80'] = true;
			}
			fclose($fp);
			
			$port = 10011;
			$waitTimeoutInSeconds = 1;
			if ($fp = fsockopen($host,$port,$errCode,$errStr,$waitTimeoutInSeconds)) {
			  $pingworked['10011'] = true;
			}
			fclose($fp);
			
			$port = 25565;
			$waitTimeoutInSeconds = 1;
			if ($fp = fsockopen($host,$port,$errCode,$errStr,$waitTimeoutInSeconds)) {
			  $pingworked['25565'] = true;
			}
			fclose($fp);
			
			$port = 27015;
			$waitTimeoutInSeconds = 1;
			if ($fp = fsockopen($host,$port,$errCode,$errStr,$waitTimeoutInSeconds)) {
			  $pingworked['27015'] = true;
			}
			fclose($fp);
			
		?>
		<center><div id="stats_main">
			<center><div id="stats_main_inner">
				<center><div class="stats_main_inner_header">
					Statistics
				</div></center>
				<center><table class="stats_main_inner_table">
					<tr>
						<td class="stats_main_inner_type">Main Server</td>
						<td class="stats_main_inner_status"><img src="<?php if($pingworked['80']){echo 'media/online.ico';}else{echo 'media/offline.jpg';};?>" class="stats_main_inner_icon"></td>
					</tr>
					<tr>
						<td class="stats_main_inner_type">Teamspeak</td>
						<td class="stats_main_inner_status"><img src="<?php if($pingworked['10011']){echo 'media/online.ico';}else{echo 'media/offline.jpg';};?>" class="stats_main_inner_icon"></td>
					</tr>
					<tr>
						<td class="stats_main_inner_type">Minecraft</td>
						<td class="stats_main_inner_status"><img src="<?php if($pingworked['25565']){echo 'media/online.ico';}else{echo 'media/offline.jpg';};?>" class="stats_main_inner_icon"></td>
					</tr>
					<tr>
						<td class="stats_main_inner_type">CounterStrike</td>
						<td class="stats_main_inner_status"><img src="<?php if($pingworked['27015']){echo 'media/online.ico';}else{echo 'media/offline.jpg';};?>" class="stats_main_inner_icon"></td>
					</tr>
				</table></center>
			</div></center>
		</div></center>
	</body>
</html>