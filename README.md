# regist.aspx.cs
This is the repository for registration
using System;
using System.Collections.Generic;
using System.Linq;
using System.Web;
using System.Web.UI;
using System.Data;
using System.Data.SqlClient;

using System.Web.UI.WebControls;

public partial class Register : System.Web.UI.Page
{
    protected void Page_Load(object sender, EventArgs e)
    {

    }
    SqlConnection con = new SqlConnection("Data Source=.;Initial Catalog=College;Integrated Security=True");
    
    protected void Button1_Click(object sender, EventArgs e)
    {
        con.Open();
        SqlCommand cmd = con.CreateCommand();
        cmd.CommandType = CommandType.Text;
        cmd.CommandText = "insert into ProductDetails values('" + TextBox1.Text + "','" + DropDownList1.Text+ "'," + TextBox2.Text + "," + TextBox3.Text + ",'" + TextBox4.Text + "')";
        cmd.ExecuteNonQuery();
        Response.Redirect("Register.aspx");
        con.Close();
        
    }
  
   
    protected void GridView1_SelectedIndexChanged1(object sender, EventArgs e)
    {

        
      
    }
    protected void Button2_Click(object sender, EventArgs e)
    {
        TextBox1.Text = "";
        DropDownList1.Text = "";
        TextBox2.Text = "";
        TextBox3.Text = "";
        TextBox4.Text = "";
    }
}
