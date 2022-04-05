# Singly_LinkedList
AddFirst ,Addlast, DeleteFirst, DeleteLast without user input

class LL
{	
	Node head;
	private int size;

	LL()
	{
		this.size=0;
	}
	class Node
	{
		String data;
		Node next;

		Node(String data)
		{
			this.data=data;
			this.next=null;
			size++;
		}
	}

	public void addF(String data)
	{
		Node newNode=new Node(data); 	
		if(head==null)
		{
			head=newNode;
			return;	
		}	
		newNode.next=head;
		head=newNode;
	}

	public void addL(String data)
	{
		Node newNode=new Node(data); 	
		if(head==null)
		{
			head=newNode;
			return;	
		}
		Node curNode=head;
		while(curNode.next !=null)
		{
			curNode=curNode.next;
		}
		curNode.next=newNode;
	}	

	public void printlist()
	{
		if(head==null)
		{
			System.out.print("LIST is empty");
			return;
		}

		Node curNode=head;
		while(curNode !=null)
		{
			System.out.print(curNode.data+"->");
			curNode=curNode.next;
		}
		System.out.print("NULL");
	}

	public void deleteF()
	{
		if(head==null)
		{
			System.out.print("LIST is empty");
			return;
		}
		size--;
		head=head.next;
		
	}

	public void deleteL()
	{
		if(head==null)
		{
			System.out.print("LIST is empty");
			return;
		}
		size--;
		if(head.next==null)
		{
			head=null;
			return;
		}

		Node secondLast=head;
		Node lastNode=head.next;
		while(lastNode.next !=null)
		{
			lastNode=lastNode.next;
			secondLast=secondLast.next;
		}
		secondLast=secondLast=null;
	}

	public int getsize()
	{
		return size;
	}
	public static void main(String args[])
	{
		LL list=new LL();
		list.addF("a");
		list.addF("is");

		list.addL("last");
		list.printlist();

		list.addF("This");
		list.printlist();

		list.deleteF();
		list.printlist();

		list.deleteL();
		list.printlist();

		System.out.println(list.getsize());
		list.addF("This");
		list.printlist();
		System.out.println(list.getsize());
	}
}
