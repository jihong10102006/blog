---
title: C#动态绑定treeview控件
date: 2012-12-18 15:57:20
tags: CSDN迁移
---
   前台只需要放一个 treeview控件就行

 后台

 

 protected void Page_Load(object sender, EventArgs e)  
 {  
 if (!IsPostBack)  
 bindTree();  
 }  
 private void bindTree()  
 {  
 DataTable dt = this.GetTreeData();  
 this.FillNode(dt, null);  
 }  
 private void FillNode(DataTable dt, TreeNode node)  
 {  
 DataView dv = new DataView(dt);  
 if (node == null) //根结点  
 {   
 dv.RowFilter = "parentid='0'"; //筛选到根结点的所有子节点  
 }  
 else //不是根结点  
 {  
 dv.RowFilter = "parentid='" + node.Value + "'"; //筛选对应节点的所有子节点  
 }  
 foreach (DataRowView drv in dv) //遍历填充节点的所有子节点，如果传入的节点node为叶子节点，遍历要退出，不再进行递归  
 {  
 TreeNode no = new TreeNode(drv["menuname"].ToString(), drv["menuid"].ToString());  
 FillNode(dt, no); //填充no节点的子节点  
 if (node == null)  
 {  
 this.TreeView1.Nodes.Add(no);  
 }  
 else  
 {  
 node.ChildNodes.Add(no);  
 }  
 }   
 }  
 private DataTable GetTreeData()  
 {  
 string strcnn = ConfigurationManager.ConnectionStrings["treecnn"].ConnectionString;  
 using (SqlConnection sqlcnn = new SqlConnection(strcnn))  
 {  
 SqlCommand sqlcmm = sqlcnn.CreateCommand();  
 sqlcmm.CommandText = "select * from MenuTree order by parentid,menuorder";  
 SqlDataAdapter da = new SqlDataAdapter(sqlcmm);  
 DataSet ds = new DataSet();  
 da.Fill(ds);  
 return ds.Tables[0];  
 }  
 }

   
   
 