using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace ConsoleALinkedListDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            LinkedList linkedList = new LinkedList();
            linkedList.head = null;
            int[] arr = { 5, 7, 11, 3 };
            for(int i=0; i< arr.Length; i++)
            {
                linkedList.head= linkedList.CreateNode(linkedList.head, arr[i]);
                linkedList.Print(linkedList.head);
            }

            Console.ReadLine();
        }
    }

    public class LinkedList
    {
        public Node head;
        public Node CreateNode(Node head, int data)
        {
            Node newNode = new Node();
            newNode.data = data;
            newNode.next = head;
            head = newNode;
            return head;
        }
        public void Print(Node head)
        {
            Console.WriteLine("Linked List:");
            while(head !=null)
            {
                Console.Write(head.data + " ");
                head = head.next;
            }

            Console.WriteLine("\n");
        }

    }

    public class Node
    {
        public int data;
        public Node next;
    }
}
