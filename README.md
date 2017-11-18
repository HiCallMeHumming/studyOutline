The following lines were added to the "OutlineEffect.cs" script:

Line 64: public Color lineColor3 = Color.yellow;
Line 86: Material outline4Material;
Line 107 and 108:
            else
                return outline4Material;
                
Line 301 and 302:
            if (outline4Material == null)
                outline4Material = CreateMaterial(new Color(1, 1, 0, 0));
                
Line 315: DestroyImmediate(outline4Material);
Line 323: outline4Material = null;



The following lines were added to the "OutlineShader.shader" script:

Line 97: bool yellow = sample1.y > h || sample2.y > h || sample3.y > h || sample4.y > h;
Line 99: if ((red && blue) || (green && blue) || (red && green) || (yellow && red) || (yellow && blue) || (yellow && green))
  (Line 99 was modified, adding the "yellow && [...]" bool to the line)
Line 147: half4 "_lineColor4"_ (the second outline is just there to end the github's italic text coding hahaha)

Line 237 to 243:
else if (sample1.y > h || sample2.y > h || sample3.y > h || sample4.y > h)
			{
				outline = _LineColor4 * _LineIntensity * _LineColor4.a;
				if (outsideDark)
					originalPixel *= 1 - _LineColor4.a;
				hasOutline = true;
			}_
      
