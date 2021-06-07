using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Drawing;
using System.Windows.Forms;

namespace GDI_BillenőGomb
{
    class MetroButton : Button

    {
        Color ledColor;
        bool checkedState;

        public Color LedColor
        {
            get => ledColor;
            set
            {
                ledColor = value;
                Invalidate();
            }
        }
        public bool CheckedState
        {
            get => checkedState;
            set
            {
                checkedState = value;
                Invalidate();
            }
        }

        public MetroButton() : base()
        {
            LedColor = Color.Blue;
            //SolidBrush blackBrush = new SolidBrush(Color.Black);
            checkedState = false;
            MinimumSize = new Size(90, 50);

        }


 



        protected override void OnPaint(PaintEventArgs pevent)
        {
            //base.OnPaint(pevent);
            Graphics gr = pevent.Graphics;
            gr.Clear(BackColor);

            //gr.DrawRectangle(new Pen(ForeColor),0,0,Width-1,Height-1);
            SizeF szovegmerete = gr.MeasureString(Text, Font);
            //gr.DrawString(Text, Font, new Pen(ForeColor).Brush,Width/2 - szovegmerete.Width/2,Height/3-szovegmerete.Height/2);
            Size ledsize = new Size(Width/2 , Height/3 );
            if (CheckedState)
            {
                gr.FillRectangle(new Pen(LedColor).Brush, Width/2- ledsize.Width/2, Height/3+szovegmerete.Height/2 +5,ledsize.Width, ledsize.Height  );
                
                
                //Újrafestjük a bal oldalit
                gr.FillRectangle(new SolidBrush(Color.Blue), Width / 2 - ledsize.Width / 2, Height / 3 + szovegmerete.Height / 2 + 5, 10, ledsize.Height);
                //rajzoljuk a jobb oldalit
                gr.FillRectangle(new SolidBrush(Color.Black), Width / 2 - ledsize.Width / 2 + ledsize.Width - 10, Height / 3 + szovegmerete.Height / 2 + 5, 10, ledsize.Height);

            }

            gr.DrawRectangle(new Pen(ForeColor), Width / 2 - ledsize.Width / 2, Height / 3 + szovegmerete.Height / 2 + 5, ledsize.Width, ledsize.Height);
            
            gr.FillRectangle(new SolidBrush(Color.Black), Width / 2 - ledsize.Width / 2, Height / 3 + szovegmerete.Height / 2 + 5, 10, ledsize.Height);



        }

        protected override void OnClick(EventArgs e)
        {
            base.OnClick(e);
            CheckedState = !CheckedState;
        }

    }
}
