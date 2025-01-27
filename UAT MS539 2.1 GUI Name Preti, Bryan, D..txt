// Name: Preti, Bryan, D.
// Date: 2025-01-27
// Program Description: GUI application with 5 different types of components, time log tracking, and an analysis of development duration.

/*
Estimated Development Time: 2 hours

Time Log:
- 2025-01-27: 1 hours (Project setup, basic GUI design)
*/

using System;
using System.Windows.Forms;

namespace GUITimeLogProject
{
    public class MainForm : Form
    {
        private Label lblMessage;
        private TextBox txtInput;
        private Button btnSubmit;
        private CheckBox chkOption;
        private ListBox lstOptions;
        private ProgressBar progressBar;

        public MainForm()
        {
            // Initialize components
            InitializeComponents();
        }

        private void InitializeComponents()
        {
            // Label
            lblMessage = new Label
            {
                Text = "Enter your name:",
                Location = new System.Drawing.Point(20, 20),
                AutoSize = true
            };
            
            // TextBox
            txtInput = new TextBox
            {
                Location = new System.Drawing.Point(20, 50),
                Width = 200
            };

            // Button
            btnSubmit = new Button
            {
                Text = "Submit",
                Location = new System.Drawing.Point(20, 90)
            };
            btnSubmit.Click += BtnSubmit_Click;

            // CheckBox
            chkOption = new CheckBox
            {
                Text = "Enable Option",
                Location = new System.Drawing.Point(20, 130),
                AutoSize = true
            };
            chkOption.CheckedChanged += ChkOption_CheckedChanged;

            // ListBox
            lstOptions = new ListBox
            {
                Location = new System.Drawing.Point(20, 170),
                Width = 200,
                Height = 100
            };
            lstOptions.Items.AddRange(new string[] { "Option 1", "Option 2", "Option 3" });

            // ProgressBar
            progressBar = new ProgressBar
            {
                Location = new System.Drawing.Point(20, 290),
                Width = 200,
                Value = 50
            };

            // Add components to the form
            this.Controls.Add(lblMessage);
            this.Controls.Add(txtInput);
            this.Controls.Add(btnSubmit);
            this.Controls.Add(chkOption);
            this.Controls.Add(lstOptions);
            this.Controls.Add(progressBar);

            // Set form properties
            this.Text = "GUI Application";
            this.StartPosition = FormStartPosition.CenterScreen;
            this.Size = new System.Drawing.Size(300, 400);
        }

        private void BtnSubmit_Click(object sender, EventArgs e)
        {
            string name = txtInput.Text;
            MessageBox.Show($"Hello, {name}!", "Greeting");
        }

        private void ChkOption_CheckedChanged(object sender, EventArgs e)
        {
            if (chkOption.Checked)
            {
                MessageBox.Show("Option Enabled", "Status");
            }
            else
            {
                MessageBox.Show("Option Disabled", "Status");
            }
        }

        [STAThread]
        static void Main()
        {
            Application.EnableVisualStyles();
            Application.SetCompatibleTextRenderingDefault(false);
            Application.Run(new MainForm());
        }
    }
}

/*
Analysis:
Estimated Development Time: 2 hours
Actual Development Time: 1 hour

The project took shorter than expected due to the limited complexity of the selected components implementation. The components chosen are some of the most widely used but functionally the most basic. The less external dependencies the easier a component is to implement typically. All these reasons combined are why the project took less time to develop than earlier anticipated.