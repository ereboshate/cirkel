package 
{
	import flash.display.Sprite;
	import flash.events.Event;
	import flash.events.KeyboardEvent;
	import flash.events.MouseEvent;
	import flash.globalization.NumberParseResult;
	import flash.text.TextField;
	

	public class Main extends Sprite 
	{
		
		
		
		private var score:int = 0;
		private var points:TextField = new TextField();
		private const NUMBER_OF_BOXES:int = 20;
		private var	v:Vector.<Sprite> = new Vector.<Sprite>;
		private var evilCircle:Sprite;
		
		public function Main():void 
		
		{
			if (stage) init();
			else addEventListener(Event.ADDED_TO_STAGE, init);
		}
		
		private function init(e:Event = null):void 
		{
			removeEventListener(Event.ADDED_TO_STAGE, init);
			// entry point
			addChild(points);
			points.text = "Points: 0";
			
			var x:int;
			var t:TextField = new TextField();
			addChild(t);
			
			
			
			for (var i:int = 0; i < NUMBER_OF_BOXES; i++) 
			{
				
				
				var s:Sprite = new Sprite();
				s.graphics.beginFill(0x0080ff);
				s.graphics.drawEllipse(0, 0, 30, 30);
				s.graphics.endFill();
				addChild(s);
				v.push(s);
				s.x = Math.random() * stage.stageWidth;
				s.y = Math.random() * stage.stageWidth;
				//s.x =  i * s.width / 2; //Math.random() * 500;
				s.addEventListener(MouseEvent.CLICK, clickbox);
			}
			evilCircle = s;
		
			stage.addEventListener(KeyboardEvent.KEY_DOWN, resetStage);
		}
		
		private function resetStage(k:KeyboardEvent):void 
		{
			
			if (k.keyCode == 32)
			{
				//Detta händer när "space" trycks ner
				score = 0;
				points.text = "Score: 0";
				
				while (v.length > 0) 
				{
					removeChild(v[0]);
					v.shift();
				}
				
				
				// fyll på igen
				for (var i:int = 0; i < NUMBER_OF_BOXES; i++) 
				{
					var s:Sprite = new Sprite();
					s.graphics.beginFill(0x0080ff);
					s.graphics.drawEllipse(0, 0, 30, 30);
					s.graphics.endFill();
					addChild(s);
					v.push(s);
					s.x = Math.random() * stage.stageWidth;
					s.y = Math.random() * stage.stageWidth;
					//s.x =  i * s.width/2; //Math.random() * 500;
					s.addEventListener(MouseEvent.CLICK, clickbox);
				}
			}
		}
		
		private function clickbox(e:MouseEvent):void 
		{
			
			if (e.target == evilCircle) 
			{
				while (v.length > 0) 
				{
					removeChild(v[0]);
					v.shift();
				}
			}
			else 
			{
				score++;
			points.text = "Score: " + score.toString();
			e.target.y = -1000;
			}
		}
		
		public function onEndClick(e:Event):void 
		{
			stage.removeEventListener (MouseEvent.CLICK, onEndClick);
			//this.removeChild(
		}
		
	}
	
}
