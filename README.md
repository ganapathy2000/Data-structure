# Data-Structure
1>>//c pgm to singly LL//
#include<iostream> <br>
#include<cstdlib> <br>
using namespace std; <br>
struct node <br>
{ <br>
 int info;<br> 
 struct node *next;<br> 
}*start; <br>
class single_llist<br> 
{ <br>
 public:<br> 
 node* create_node(int);<br> 
 void insert_begin(); <br>
 void insert_last(); <br>
 void insert_pos();<br> 
 void delete_begin(); <br>
 void delete_last(); <br>
 void delete_pos(); <br>
 void update_begin(); <br>
 void update_last();<br> 
 void update_pos();<br> 
 void sort(); <br>
 void reverse(); <br>
 void search(); <br>
 void display(); <br>
 single_llist() <br>
 { <br>
 start = NULL;<br> 
 } <br>
}; <br>
int main() <br>
{ <br>
 int choice; <br>
 single_llist sl,s2; <br>
 start = NULL; <br>
 do <br>
 { <br>
 cout<<"---------------------------------"<<endl;<br> 
 cout<<"Operations on singly linked list"<<endl;<br> 
 cout<<"---------------------------------"<<endl; <br>
 cout<<"1.Insert at first"<<endl; <br>
 cout<<"2.Insert at last"<<endl;<br> 
 cout<<"3.Insert at position"<<endl;<br> 
 cout<<"4.Delete at first"<<endl; <br>
 cout<<"5.Delete at Last"<<endl;<br> 
 cout<<"6.Delete at position"<<endl; <br>
 cout<<"7.Update at first"<<endl; <br>
 cout<<"8.Update at last"<<endl; <br>
 cout<<"9.Update at position"<<endl;<br> 
 cout<<"10.Ascending order"<<endl;<br> 
 cout<<"11.Descending order"<<endl; <br>
 cout<<"12.Search"<<endl; <br>
 cout<<"13.Display"<<endl;<br> 
 cout<<"14.Exit "<<endl; <br>
 cout<<"Enter your choice :";<br> 
 cin>>choice; <br>
 switch(choice) <br>
 {<br> 
 case 1: sl.insert_begin(); <br>
 sl.display(); <br>
 break;<br> 
 case 2: sl.insert_last();<br> 
 sl.display(); <br>
 break;<br> 
 case 3: sl.insert_pos(); <br>
 sl.display(); <br>
 break; <br>
 case 4: s2.delete_begin(); <br>
 sl.display(); <br>
 break; <br>
 case 5: s2.delete_last(); <br>
 sl.display(); <br>
 break; <br>
 case 6: sl.delete_pos(); <br>
 sl.display(); <br>
 break; <br>
 case 7: sl.update_begin(); <br>
 sl.display(); <br>
 break; <br>
 case 8: sl.update_last(); <br>
 sl.display(); <br>
 break; <br>
 case 9: sl.update_pos(); <br>
 sl.display(); <br>
 break; <br>
 case 10:sl.sort(); <br>
 sl.display(); <br>
 break; <br>
 case 11:sl.reverse(); <br>
 sl.display(); <br>
 break; <br>
 case 12:sl.search(); <br>
 sl.display(); <br>
 break; <br>
 case 13:sl.display(); <br>
 break; <br>
 case 14:exit(0); <br>
 break; <br>
 default:cout<<"Wrong choice...???"<<endl; <br>
 break; <br>
 } <br>
 } <br>
 while(choice != 14); <br>
} <br>
node *single_llist::create_node(int value)<br> 
{ <br>
 struct node *temp, *s; <br>
 temp = new(struct node); <br>
 if (temp == NULL) <br>
 { <br>
 cout<<"Memory not allocated"<<endl; <br>
 return 0; <br>
 } <br>
 else <br>
 { <br>
 temp->info = value; <br>
 temp->next = NULL; <br>
 return temp; <br>
 } <br>
} <br>
void single_llist::insert_begin() <br>
{ <br>
 int value; <br>
 cout<<"Enter the value to be inserted : "; <br>
 cin>>value; <br>
 struct node *temp, *s; <br>
 temp = create_node(value); <br>
 if (start == NULL) <br>
 { <br>
 start = temp; <br>
 start->next = NULL; <br>
 cout<<temp->info<<" is inserted at first in the empty list"<<endl; <br>
 } <br>
 else <br>
 { <br>
 s = start; <br>
 start = temp; <br>
 start->next = s; <br>
 cout<<temp->info<<" is inserted at first"<<endl; <br>
 } <br>
}<br>
void single_llist::insert_last() <br>
{ <br>
 int value; <br>
 cout<<"Enter the value to be inserted : "; <br>
 cin>>value; <br>
 struct node *temp, *s; <br>
 temp = create_node(value); <br>
 if (start == NULL) <br>
 { <br>
 start = temp; <br>
 start->next = NULL;<br>
 cout<<temp->info<<" is inserted at last in the empty list"<<endl; <br>
 } <br>
 else <br>
 { <br>
 s = start; <br>
 while (s->next != NULL)<br> 
 { <br>
 s = s->next; <br>
 } <br>
 temp->next = NULL; <br>
 s->next = temp; <br>
 cout<<temp->info<<" is inserted at last"<<endl; <br>
 } <br>
} <br>
void single_llist::insert_pos() <br>
{ <br>
 int value, pos, counter = 0, loc = 1; <br>
 struct node *temp, *s, *ptr; <br>
 s = start; <br>
 while (s != NULL) <br>
 { <br>
 s = s->next; <br>
 counter++; <br>
 } <br>
 if (counter == 0){} <br>
 else <br>
 { <br>
 cout<<"Enter the postion from "<<loc<<" to "<<counter+1<<" : "; <br>
 cin>>pos; <br>
 s = start; <br>
 if(pos == 1) <br>
 { <br>
 cout<<"Enter the value to be inserted : "; <br>
 cin>>value; <br>
 temp = create_node(value); <br>
 start = temp; <br>
 start->next = s; <br>
 cout<<temp->info<<" is inserted at first"<<endl; <br>
 } <br>
 else if (pos > 1 && pos <= counter) <br>
 { <br>
 cout<<"Enter the value to be inserted : "; <br>
 cin>>value; <br>
 temp = create_node(value); <br>
 for (int i = 1; i < pos; i++) <br>
 { <br>
 ptr = s; <br>
 s = s->next; <br>
 } <br>
 ptr->next = temp; <br>
 temp->next = s; <br>
 cout<<temp->info<<" is inserted at position "<<pos<<endl; <br>
 } <br>
 else if (pos == counter+1) <br>
 { <br>
 cout<<"Enter the value to be inserted : "; <br>
 cin>>value; <br>
 temp = create_node(value); <br>
 while (s->next != NULL) <br>
 { <br>
 s = s->next; <br>
 } <br>
 temp->next = NULL;<br> 
 s->next = temp;<br> 
 cout<<temp->info<<" is inserted at last"<<endl; <br>
 } <br>
 else <br>
 { <br>
 cout<<"Positon out of range...!!!"<<endl; <br>
 } <br>
 } <br>
} <br>
void single_llist::delete_begin() <br>
{ <br>
 if (start == NULL){} <br>
 else <br>
 { <br>
 struct node *s, *ptr; <br>
 s = start; <br>
 start = s->next; <br>
 cout<<s->info<<" deleted from first"<<endl;<br> 
 free(s); <br>
 } <br>
} <br>
void single_llist::delete_last() <br>
{ <br>
 int i, counter = 0; <br>
 struct node *s, *ptr; <br>
 if (start == NULL){} <br>
 else <br>
 { <br>
 s = start; <br>
 while (s != NULL) <br>
 { <br>
 s = s->next; <br>
 counter++; <br>
 } <br>
 s = start; <br>
 if (counter == 1) <br>
 { <br>
 start = s->next; <br>
 cout<<s->info<<" deleted from last"<<endl; <br>
 free(s); <br>
 } <br>
 else<br> 
 { <br>
 for (i = 1;i < counter;i++) <br>
 { <br>
 ptr = s; <br>
 s = s->next; <br>
 } <br>
 ptr->next = s->next; <br>
 cout<<s->info<<" deleted from last"<<endl; <br>
 free(s); <br>
 } <br>
 } <br>
} <br>
void single_llist::delete_pos() <br>
{ <br>
 int pos, i, counter = 0, loc = 1; <br>
 struct node *s, *ptr; <br><br>
 s = start; <br>
 while (s != NULL) <br>
 { <br>
 s = s->next; <br>
 counter++; <br>
 } <br>
 if (counter == 0){} <br>
 else <br>
 { <br>
 if (counter == 1) <br>
 { <br>
 cout<<"Enter the postion [ SAY "<<loc<<" ] : "; <br>
 cin>>pos; <br>
 s = start; <br>
 if (pos == 1) <br>
 { <br>
 start = s->next; <br>
 cout<<s->info<<" deleted from first"<<endl; <br>
 free(s); <br>
 } <br>
 else <br>
 cout<<"Position out of range...!!!"<<endl; <br>
 } <br>
 else<br> 
 { <br>
 cout<<"Enter the postion from "<<loc<<" to "<<counter<<" : ";<br> 
 cin>>pos;<br> 
 s = start; <br>
 if (pos == 1) <br>
 { <br>
 start = s->next; <br>
 cout<<s->info<<" deleted from first"<<endl;<br> 
 free(s); <br>
 } <br>
 else if (pos > 1 && pos <= counter) <br>
 { <br>
 for (i = 1;i < pos;i++) <br>
 { <br>
 ptr = s; <br>
 s = s->next; <br>
 } <br>
 ptr->next = s->next; <br>
 if(pos == counter) <br>
 {cout<<s->info<<" deleted from last"<<endl; <br>
 free(s);} <br>
 else <br>
 {cout<<s->info<<" deleted from postion "<<pos<<endl;<br> 
 free(s);} <br>
 } <br>
 else <br>
 cout<<"Position out of range...!!!"<<endl; <br>
 } <br>
 } <br>
} <br>
void single_llist::update_begin() <br>
{ <br>
 int value, pos=1, i,counter = 0; <br>
 struct node *s, *ptr; <br>
 s = start; <br>
 while (s != NULL) <br>
 { <br>
 s = s->next; <br>
 counter++; <br>
 } <br>
 if (counter == 0){} <br>
 else if (pos == 1) <br>
 { <br>
 cout<<"Enter the new node : "; <br>
 cin>>value; <br>
 start->info = value; <br>
 cout<<"Node updated at first position : "<<pos<<" = "<<start->info<<endl; <br>
 } <br>
} <br>
void single_llist::update_last() <br>
{ <br>
 int value, pos, i,counter = 0; <br>
 struct node *s, *ptr;<br> 
 s = start; <br>
 while (s != NULL) <br>
 { <br>
 s = s->next; <br>
 counter++; <br>
 } <br>
 s=start; <br>
 if (counter == 0){} <br>
 else <br>
 { <br>
 cout<<"Enter the new node : "; <br>
 cin>>value; <br>
 for (i = 1; i < counter ; i++) <br>
 { <br>
 s = s->next; <br>
 } <br>
 s->info = value; <br>
 cout<<"Node updated at last position : "<<counter<<" = "<<s->info<<endl; <br>
 } <br>
} <br>
void single_llist::update_pos()<br> 
{ <br>
 int value, pos, i,counter = 0, loc = 1; <br>
 struct node *s, *ptr;<br> 
 s = start; <br>
 while (s != NULL) <br>
 { <br>
 s = s->next; <br>
 counter++; <br>
 } <br>
 if (counter == 0){} <br>
 else<br> 
 { <br>
 if (counter == 1) <br>
 { <br>
 cout<<"Enter the postion [ SAY "<<loc<<" ] : "; <br>
 cin>>pos;<br>
 s = start; <br>
 if (pos == 1) <br>
 { <br>
 cout<<"Enter the new node : "; <br>
 cin>>value; <br>
 start->info = value; <br>
 cout<<"Node updated at position : "<<pos<<" = "<<start->info<<endl; <br>
 } <br>
 else <br>
 cout<<"Position out of range...!!!"<<endl; <br>
 } <br>
 else <br>
 { <br>
 cout<<"Enter the postion from "<<loc<<" to "<<counter<<" : "; <br>
 cin>>pos; <br>
 s = start; <br>
 if (pos == 1) <br>
 { <br>
 cout<<"Enter the new node : "; <br>
 cin>>value; <br>
 start->info = value; <br>
 cout<<"Node updated at position : "<<pos<<" = "<<start->info<<endl;<br> 
 } <br>
 else if (pos > 1 && pos <= counter) <br>
 { <br>
 cout<<"Enter the new node : "; <br>
 cin>>value; <br>
 for (i = 1; i < pos ; i++) <br>
 { <br>
 s = s->next;<br> 
 }<br> 
 s->info = value; <br>
 cout<<"Node updated at position : "<<pos<<" = "<<s->info<<endl; <br>
 } <br>
 else <br>
 cout<<"Position out of range...!!!"<<endl; <br>
 }<br>
 }<br>
} <br>
void single_llist::sort() <br>
{<br> 
 struct node *ptr, *s;<br>
 int value; <br>
 if (start == NULL){} <br>
 else <br>
 { <br>
 ptr = start; <br>
 while (ptr != NULL) <br>
 { <br>
 for (s = ptr->next;s !=NULL;s = s->next) <br>
 { <br>
 if (ptr->info > s->info) <br>
 { <br>
 value = ptr->info; <br>
 ptr->info = s->info;<br> 
 s->info = value;<br> 
 }<br> 
 } <br>
 ptr = ptr->next; <br>
} <br>
 } <br>
}<br> 
void single_llist::reverse() <br>
{ <br>
 struct node *ptr, *s; <br>
 int value; <br>
 if (start == NULL){}<br> 
 else <br>
 { <br>
 ptr = start; <br>
 while (ptr != NULL) <br>
 { <br>
 for (s = ptr->next;s !=NULL;s = s->next) <br>
 {<br> 
 if (ptr->info < s->info) <br><br>
 { <br>
 value = ptr->info; <br>
 ptr->info = s->info;<br> 
 s->info = value; <br>
 } <br>
 } <br>
 ptr = ptr->next;<br> 
 }<br><br> 
 }<br> 
}<br> 
void single_llist::search()<br> 
{<br> 
 int value, loc = 0, pos = 0, counter = 0;<br> 
 struct node *s;<br> 
 s = start; <br>
 while (s != NULL) <br><br>
 {<br> 
 s = s->next; <br>
 counter++; <br>
 }<br> 
 if (start == NULL){}<br> 
 else<br> 
 { <br>
 cout<<"Enter the value to be searched : "; <br>
 cin>>value;<br> 
 struct node *s; <br>
 s = start;<br> 
 while (s != NULL) <br>
 { <br>
 pos++; <br>
 if (s->info == value) <br>
 {<br> 
 loc++;<br> 
 if(loc == 1)<br> 
 cout<<"Element "<<value<<" is found at position "<<pos; <br>
 else if(loc <= counter)<br> 
 cout<<" , "<<pos; <br>
 }<br> 
 s = s->next;<br> 
 } <br><br>
 cout<<endl; <br>
 if (loc == 0) <br>
 cout<<"Element "<<value<<" not found in the list"<<endl; <br>
 } <br>
} <br>
void single_llist::display() <br>
{ <br>
 struct node *temp; <br>
 if (start == NULL) <br>
 cout<<"Linked list is empty...!!!"<<endl; <br>
 else <br>
 { <br>
 cout<<"Linked list contains : "; <br>
 temp = start; <br>
 while (temp != NULL) <br>
 { <br>
 cout<<temp->info<<" "; <br>
 temp = temp->next; <br>
 } <br>
 cout<<endl; <br>
 } <br>
}<br>
 Output:<br>
 1-<br>
  ![L1](https://user-images.githubusercontent.com/98145090/152733801-143ad317-dd55-4c52-9714-9ba496e29845.png)<br>
 2-<br>
 ![L2](https://user-images.githubusercontent.com/98145090/152733827-c7b324fc-6b1b-4eb4-a283-a3daeacbd45c.png)<br>
 3-<br>
  ![L3](https://user-images.githubusercontent.com/98145090/152733844-0ad2a0ef-4d3e-4dbd-abe5-eb9344224340.png)<br>
 4-<br>
  ![L4](https://user-images.githubusercontent.com/98145090/152733868-740fda43-9445-477d-87c5-9179789d5b35.png)<br>
 5-<br>
  ![L5](https://user-images.githubusercontent.com/98145090/152733887-4f8e6c7d-8106-47d6-8f80-162ae175e5ad.png)<br>
 6-<br>
 ![L6](https://user-images.githubusercontent.com/98145090/152733927-1e066f5f-7fac-46d2-b045-be87722d398a.png) <br>
 7-<br>
 ![L7](https://user-images.githubusercontent.com/98145090/152733950-8826d02c-3f5a-4deb-a7b8-efa3162840ce.png)<br>
 8-<br>
 ![L8](https://user-images.githubusercontent.com/98145090/152733970-b758f3e8-80de-4048-a712-d0a51850250e.png)<br>
 +++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++<br>
 //2. Write a C++ program to split the linked list into two halves such that the element ‘e’ should be the first element of second list.//<br>
#include<iostream><br>
using namespace std;<br>
struct Node<br>
{<br>
int value;<br>
struct Node *next;<br>
};<br>
struct Node* head = NULL;<br>
struct Node* sHead = NULL;<br>
struct Node* temp = NULL;<br>
void insert(int new_data)<br>
{<br>
struct Node* new_node = new Node();<br>
new_node->value = new_data;<br>
new_node->next = head;<br>
head = new_node;<br>
}<br>
int n;<br>
int ele;<br>
int splitIndex;<br>
int main()<br>
{<br>
int i;<br>
cout<<"Enter number of elements you want in the list\t";<br>
cin>>n;<br>
cout<<"Enter elements :" <<endl;<br>
for(i=0;i<n;i++)<br>
{<br>
cin>>ele;<br>
insert(ele);<br>
}<br>
cout<<"\nList of elements : "<<endl;<br>
Node *t;<br>
t = head;<br>
while(t != NULL)<br>
{<br>
cout<<t->value<<"\t";<br>
t = t->next;<br>
}<br>
cout<<"\n\nEnter the position you want the list to split ";<br>
cin>>splitIndex;<br>
while(splitIndex < 0 || splitIndex > n-1)<br>
{<br>
cout<<"Invalid position. Try again."<<endl;<br>
cin>>splitIndex;<br>
}<br>
temp = head;<br>
for(i=0;i<=splitIndex;i++)<br>
{<br>
if(i==splitIndex-1)<br>
{<br>
Node *tN;<br>
tN = temp->next;<br>
sHead = tN;<br>
temp->next = NULL;<br>
break;<br>
}<br>
temp = temp->next;<br>
}<br>
temp = head;<br>
if(temp == NULL)<br>
{<br>
cout<<"\nFirst list is empty"<<endl;<br>
}<br>
else<br><br>
{<br><br>
cout<<"\n\nFirst list element "<<endl;<br>
while(temp != NULL)<br>
{<br>
cout<<temp->value<<"\t";<br>
temp = temp->next;<br>
}<br>
}<br>
temp = sHead;<br>
if(temp == NULL)<br>
{<br>
cout<<"\nSecond list is empty"<<endl;<br>
 }<br>
 else<br>
 {<br>
cout<<"\n\nSecond list elements "<<endl;<br>
while(temp != NULL)<br>
{<br>
cout<<temp->value<<"\t";<br>
temp = temp->next;<br>
}<br>
}<br>
return 0;<br>
}<br>

 Output:<br>
		    
		    
![LINKll](https://user-images.githubusercontent.com/98145090/154898424-b4cdb703-b0ec-412a-92ec-245d8c714607.png)<br>
		    
 +++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++<br>
3>>//Hashing//<br>
	#include<iostream><br>
#include<limits.h><br>
using namespace std;<br>
void Insert(int ary[],int hFn, int Size){<br>
    int element,pos,n=0;<br>
cout<<"Enter key element to insert\n";<br>
cin>>element;<br>
pos = element%hFn; <br>
while(ary[pos]!= INT_MIN) {  <br>
if(ary[pos]== INT_MAX)<br>
            break;<br>
pos = (pos+1)%hFn;<br>
n++;<br>
if(n==Size)<br>
            break; <br>    
}<br>
if(n==Size)<br>
        cout<<"Hash table was full of elements\nNo Place to insert this element\n\n";<br>
else<br>
        ary[pos] = element;   <br> 
}<br>
void display(int ary[],int Size){<br>
int i;<br>
 <br>
cout<<"Index\tValue\n";<br>
for(i=0;i<Size;i++)<br>
        cout<<i<<"\t"<<ary[i]<<"\n";<br>
}<br>
int main(){<br>
int Size,hFn,i,choice;<br>
cout<<"Enter size of hash table\n";<br>
cin>>Size;<br>
 hFn=Size;<br>
int ary[Size];<br>
for(i=0;i<Size;i++)<br>
        ary[i]=INT_MIN; <br>
do{<br>
cout<<"Enter your choice\n";<br>
cout<<" 1-> Insert\n 2-> Display\n 0-> Exit\n";<br>
cin>>choice;<br>
switch(choice){<br>
case 1:<br>
Insert(ary,hFn,Size);<br>
break;<br>
case 2:<br>
display(ary,Size);<br>
break;<br>
default:<br>
cout<<"Enter correct choice\n";<br>
break;<br>
}<br>
}while(choice);<br>
return 0;<br>
}<br>

	Output:<br>
	![image](https://user-images.githubusercontent.com/98145098/165684131-dd3778a5-451b-4bcd-9a39-c056971e5a99.png)
![image](https://user-images.githubusercontent.com/98145098/165684207-ced9dea2-a7b9-4d2f-8cc0-9b5064b7731f.png)


<br>
	++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++<br>
4>>//Merge sort//<br>
 #include <iostream><br>
#include<conio><br>
void Merge(int *a, int low, int high, int mid)<br>
{<br>
	int i, j, k, temp[high-low+1];<br>
	i = low;<br>
	k = 0;<br>
              j = mid + 1;<br>
             while (i <= mid && j <= high)<br>
	{<br>
		if (a[i] < a[j])<br>
		{<br>
			temp[k] = a[i];<br>
			k++;<br>
			i++;<br>
		}<br>
		else<br>
		{<br>
			temp[k] = a[j];<br>
			k++;<br>
			j++;<br>
		}<br>
	}<br>
	while (i <= mid)<br>
	{<br>
		temp[k] = a[i];
		k++;<br>
		i++;<br>
	}<br>
	while (j <= high)<br>
	{<br>
		temp[k] = a[j];<br>
		k++;<br>
		j++;<br>
	}<br>
	for (i = low; i <= high; i++)<br>
	{<br>
		a[i] = temp[i-low];<br>
	}<br>
}<br>
void MergeSort(int *a, int low, int high)<br>
{<br>
	int mid;<br>
	if (low < high)<br>
	{<br>
		mid=(low+high)/2;<br>
			MergeSort(a, low, mid);<br>
		              MergeSort(a, mid+1, high);<br>
			Merge(a, low, high, mid);<br>
	}<br>
}<br>
void main()<br>
{<br>
	int n, i;<br>
	cout<<"\nEnter the number of data element to be sorted: ";<br>
	cin>>n;<br>
 
	int arr[n];<br>
	for(i = 0; i < n; i++)<br>
	{<br>
		cout<<"Enter element "<<i+1<<": ";<br>
		cin>>arr[i];<br>
	}<br>
                           MergeSort(arr, 0, n-1);<br>
		cout<<"\nSorted Data ";<br>
	           for (i = 0; i < n; i++)<br>
                         cout<<"->"<<arr[i];<br>
 
	       getch();<br>
}<br>

Output:
![image](https://user-images.githubusercontent.com/98145090/165239002-f3d23a3b-1584-4443-bc2f-e33309807e06.png)<br>
 +++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++<br>
 5>>//N Queen's problem//<br>
	#define N 8<br>
#include <stdbool.h><br>
#include <stdio.h><br>
void printSolution(int board[N][N])<br>
{<br>
for (int i = 0; i < N; i++) {<br>
for (int j = 0; j < N; j++)<br>
printf(" %d ", board[i][j]);<br>
printf("\n");<br>
}<br>
}<br>
bool isSafe(int board[N][N], int row, int col)<br>
{<br>
int i, j;<br>
for (i = 0; i < col; i++)<br>
if (board[row][i])<br>
return false;<br>
for (i = row, j = col; i >= 0 && j >= 0; i--, j--)<br>
if (board[i][j])<br>
return false;<br>
for (i = row, j = col; j >= 0 && i < N; i++, j--)<br>
if (board[i][j])<br>
return false;<br>
return true;<br>
}<br>
bool solveNQUtil(int board[N][N], int col)<br>
{<br>
if (col >= N)<br>
return true;<br>
for (int i = 0; i < N; i++) {<br>
if (isSafe(board, i, col)) {<br>
board[i][col] = 1;<br>
if (solveNQUtil(board, col + 1))<br>
return true;<br>
board[i][col] = 0; }<br>
}<br>
return false;<br>
}<br>
bool solveNQ()<br>
{<br>
int board[N][N]; <br>
for(int i=0;i<N;i++){<br>
for(int j=0;j<N;j++){<br>
board[i][j] = 0;<br>
}<br>
}<br>
if (solveNQUtil(board, 0) == false) {<br>
printf("Solution does not exist");<br>
return false;<br>
}<br>
printSolution(board);<br>
return true;<br>
}<br>
int main()<br>
{<br>
solveNQ();<br>
return 0;<br>
}<br>
Output: ![image](https://user-images.githubusercontent.com/98145090/165240794-e5c709aa-8bf7-403a-a7fd-f751e0e76495.png)<br>
		    
		    
	++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++<br>
	6>>//DFS//<br>
	#include <bits/stdc++.h><br>
using namespace std;<br>
class Graph<br>
{<br>
public:<br>
map<int, bool> visited;<br>
map<int, list<int>> adj;<br>
void addEdge(int v, int w);<br>
void DFS(int v);<br>
};<br>
void Graph::addEdge(int v, int w)<br>
{<br>
adj[v].push_back(w); <br>
adj[w].push_back(v);<br>
}<br>
void Graph::DFS(int v)<br>
{<br>
visited[v] = true;<br>
cout << v << " ";<br>
list<int>::iterator i;<br>
for (i = adj[v].begin(); i != adj[v].end(); ++i)<br>
if (!visited[*i])<br>
DFS(*i);<br>
}<br>
int main()<br>
{<br>
Graph g;<br>
g.addEdge(0, 1);<br>
g.addEdge(0, 2);<br>
g.addEdge(1, 2);<br>
g.addEdge(2, 0);<br>
g.addEdge(2, 3);<br>
g.addEdge(3, 3);<br>
cout << "Following is Depth First Traversal"<br>
" (starting from vertex 2) \n";<br>
g.DFS(2);<br>
return 0;<br>
}<br>
Output:
	![image](https://user-images.githubusercontent.com/98145090/165241644-29182965-b29c-4cf1-99e2-7cbe641b2e4d.png)
<br>
	+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++<br>

7.Write a C++ program to implement doubly linked list.
#include<stdio.h><br><br>
	#include<stdlib.h><br><br>
	struct node<br><br>
	{<br><br>
	struct node *prev;<br><br>
	struct node *next;<br><br>
	int data;<br><br>
	};<br><br>
	struct node *head;<br><br>
	void insertion_beginning();<br><br>
	void insertion_last();<br><br>
	void insertion_specified();<br><br>
	void deletion_beginning();<br><br>
	void deletion_last();<br><br>
	void deletion_specified();<br><br>
	void display();<br><br>
	void search();<br><br>
	int main ()<br><br>
	{<br><br>
	int choice =0;<br><br>
	while(choice != 9)<br><br>
	{
	printf("\nChoose one option from the following list ...\n");<br><br>
	printf("\n1.Insert in begining\n2.Insert at last\n3.Insert at any random location\n4.Delete from Beginning\n5.Delete from last\n6.Delete the node after the given data\n7.Search\n8.Show\n9.Exit\n");<br>
	printf("\nEnter your choice?\n");<br>
	scanf("\n%d",&choice);<br>
	switch(choice)<br>
	{<br>
	case 1:<br>
	insertion_beginning();<br>
	break;<br>
	case 2:<br>
	insertion_last();<br>
	break;<br>
	case 3:<br>
	insertion_specified();<br>
	break;<br>
	case 4:<br>
	deletion_beginning();<br>
	break;<br>
	case 5:<br>
	deletion_last();<br>
	break;<br>
	case 6:<br>
	deletion_specified();<br>
	break;<br>
	case 7:<br>
	search();<br>
	break;<br>
	case 8:<br>
	display();<br>
	break;<br>
	case 9:<br>
	exit(0);<br>
	break;<br>
	default:<br>
	printf("Please enter valid choice..");<br>
	}<br>
	}<br>
	}<br>
	void insertion_beginning()
	{
	struct node *ptr;
	int item;
	ptr = (struct node *)malloc(sizeof(struct node));
	if(ptr == NULL)
	{
	printf("\nOVERFLOW");
	}
	else
	{
	printf("\nEnter Item value");
	scanf("%d",&item);
	
	if(head==NULL)
	{
	ptr->next = NULL;
	ptr->prev=NULL;
	ptr->data=item;
	head=ptr;
	}
	else
	{
	ptr->data=item;
	ptr->prev=NULL;
	ptr->next = head;
	head->prev=ptr;
	head=ptr;
	}
	printf("\nNode inserted\n");
	}
	}
	void insertion_last()
	{
	struct node *ptr,*temp;
	int item;
	ptr = (struct node *) malloc(sizeof(struct node));
	if(ptr == NULL)
	{
	printf("\nOVERFLOW");
	}
	else
	{
	printf("\nEnter value");
	scanf("%d",&item);
	ptr->data=item;
	if(head == NULL)
	{
	ptr->next = NULL;
	ptr->prev = NULL;
	head = ptr;
	}
	else
	{
	temp = head;
	while(temp->next!=NULL)
	{
	temp = temp->next;
	}
	temp->next = ptr;
	ptr ->prev=temp;
	ptr->next = NULL;
	}
	}
	printf("\nnode inserted\n");
	}
	void insertion_specified()
	{
	struct node *ptr,*temp;
	int item,loc,i;
	ptr = (struct node *)malloc(sizeof(struct node));
	if(ptr == NULL)
	{
	printf("\n OVERFLOW");
	}
	else
	{
	temp=head;
	printf("Enter the location");
	scanf("%d",&loc);
	for(i=0;i<loc;i++)
	{
	temp = temp->next;
	if(temp == NULL)
	{
	printf("\n There are less than %d elements", loc);
	return;
	}
	}
	printf("Enter value");
	scanf("%d",&item);
	ptr->data = item;
	ptr->next = temp->next;
	ptr -> prev = temp;
	temp->next = ptr;
	temp->next->prev=ptr;
	printf("\nnode inserted\n");
	}
	}
	void deletion_beginning()
	{
	struct node *ptr;
	if(head == NULL)
	{
	printf("\n UNDERFLOW");
	}
	else if(head->next == NULL)
	{
	head = NULL;
	free(head);
	printf("\nnode deleted\n");
	}
	else
	{
	ptr = head;
	head = head -> next;
	head -> prev = NULL;
	free(ptr);
	printf("\nnode deleted\n");
	}
	}
	void deletion_last()
	{
	struct node *ptr;
	if(head == NULL)
	{
	printf("\n UNDERFLOW");
	}
	else if(head->next == NULL)
	{
	head = NULL;
	free(head);
	printf("\nnode deleted\n");
	}
	else
	{
	ptr = head;
	if(ptr->next != NULL)
	{
	ptr = ptr -> next;
	}
	ptr -> prev -> next = NULL;
	free(ptr);
	printf("\nnode deleted\n");
	}
	}
	void deletion_specified()
	{
	struct node *ptr, *temp;
	int val;
	printf("\n Enter the data after which the node is to be deleted : ");
	scanf("%d", &val);
	ptr = head;
	while(ptr -> data != val)
	ptr = ptr -> next;
	if(ptr -> next == NULL)
	{
	printf("\nCan't delete\n");
	}
	else if(ptr -> next -> next == NULL)
	{
	ptr ->next = NULL;
	}
	else
	{
	temp = ptr -> next;
	ptr -> next = temp -> next;
	temp -> next -> prev = ptr;
	free(temp);
	printf("\nnode deleted\n");
	}
	}
	void display()
	{
	struct node *ptr;
	printf("\n printing values...\n");
	ptr = head;
	while(ptr != NULL)
	{
	printf("%d\n",ptr->data);
	ptr=ptr->next;
	}
	}
	void search()
	{
	struct node *ptr;
	int item,i=0,flag;
	ptr = head;
	if(ptr == NULL)
	{
	printf("\nEmpty List\n");
	}
	else
	{
	printf("\nEnter item which you want to search?\n");
	scanf("%d",&item);
	while (ptr!=NULL)
	{
	if(ptr->data == item)
	{
	printf("\nitem found at location %d ",i+1);
	flag=0;
	break;
	}
	else
	{
	flag=1;
	}
	i++;
	ptr = ptr -> next;
	}
	if(flag==1)
	{
	printf("\nItem not found\n");
	}
	}
	}


8.Find the subset of a given set S = {S1,S2,S3,………,Sn} OF ‘n’ positive integers whose sum is equal to a given positive integer d.<br>
#include<iostream><br>
using namespace std;<br>
int s[10],d,n,set[10],count=0;<br>
void display(int);<br>
int flag = 0;<br>
int main()<br>
{<br>
 int subset(int,int);<br>
 int i;<br>
  cout<<"ENTER THE NUMBER OF THE ELEMENTS IN THE SET : ";<br>
 cin>>n;<br>
 cout<<"ENTER THE SET OF VALUES : ";<br>
 for(i=0;i<n;i++)<br>
   cin>>s[i];<br>
 cout<<"ENTER THE SUM : ";<br>
 cin>>d;<br>
 cout<<"THE PROGRAM OUTPUT IS: ";<br>
 subset(0 , 0);<br>
 if(flag == 0)<br>
 cout<<"There is no solution";<br>
 }<br>
int subset(int sum,int i)<br>
{<br><br><br>
if(<br>sum == d)<br><br>
{<br>
 flag = 1;<br>
 display(count);<br>
 return 0;<br>
}<br>
if(sum>d || i>=n)<br>
return 1;<br>
else<br>
{<br><br>
 set[count]=s[i];<br>
 count++;<br>
 subset(sum+s[i],i+1);<br>
 count--;<br>
 subset(sum,i+1);<br>
}<br>
}<br>
void display(int count)<br>
{<br>
 int i;<br>
 cout<<"\t{";<br>
 for(i=0;i<count;i++)<br>
 cout<<set[i];<br>
 cout<<"}";<br>
}<br>


9.Write a program to Insert into and Delete from a Binary Search Tree.
#include<iostream><br>
using namespace std;<br>
struct node<br>
{<br>
	int info;<br>
	struct node*left;<br>
	struct node*right;<br>
}*root;<br>
class BST <br>
{ <br>
 public:<br> 
 void insert(node *, node *); 
 void inorder(node *); 
 void postorder(node *); 
 void display(node *, int); 
 BST() 
 { 
 root = NULL; 
 } 
};
int main() 
{ 
 int choice, num; 
 BST bst; 
 node *temp; 
 while (1) 
 { 
cout<<"1.Insert Element "<<endl; <br>
 cout<<"2.Inorder Traversal"<<endl;  <br>
 cout<<"3.Display"<<endl; <br>
 cout<<"4.Quit"<<endl; <br>
 cout<<"Enter your choice : ";<br> 
 cin>>choice; <br>
 switch(choice) <br>
 { <br>
 case 1:<br> 
 temp = new node;<br> 
 cout<<"Enter the number to be inserted : ";<br> 
 cin>>temp->info; <br>
 bst.insert(root, temp);<br> 
 break;  <br>
 case 2: <br>
 cout<<"Inorder Traversal of BST:"<<endl;<br> 
 bst.inorder(root); <br>
 cout<<endl; <br>
 break; <br>
 case 3: <br>
 cout<<"Display BST:"<<endl;<br> 
 bst.display(root,1); <br>
 cout<<endl; <br>
 break; <br>
 case 4: <br>
 exit(1); <br>
 default: <br>
 cout<<"Wrong choice"<<endl;<br> 
 } <br>
 } <br>
} <br>
void BST::insert(node *tree, node *newnode)<br> 
{ <br>
 if (root == NULL)<br> 
 { <br>
 root = new node;<br> 
 root->info = newnode->info;<br> 
 root->left = NULL; <br>
 root->right = NULL; <br>
 cout<<"Root Node is Added"<<endl;<br> 
 return; <br>
 } <br>
 if (tree->info == newnode->info)<br> 
 { <br>
 cout<<"Element already in the tree"<<endl; <br>
 return; <br>
 } <br>
 if (tree->info > newnode->info)<br> 
{ <br>
 if (tree->left != NULL) <br>
 { <br>
 insert(tree->left, newnode);<br> 
 } <br>
 else <br>
 { <br>
 tree->left = newnode;<br> 
 (tree->left)->left = NULL;<br> 
 (tree->left)->right = NULL; <br>
 cout<<"Node Added To Left"<<endl;<br> 
 return; <br>
 } <br>
 } <br>
 else <br>
 { <br>
 if (tree->right != NULL)<br> 
 { <br>
 insert(tree->right, newnode); <br>
 } <br>
 else <br>
 { <br>
 tree->right = newnode; <br>
 (tree->right)->left = NULL;<br> 
 (tree->right)->right = NULL; <br>
 cout<<"Node Added To Right"<<endl;<br> 
 return; <br>
 } <br>
 } <br>
} <br>
void BST::inorder(node *ptr)<br> 
{ <br>
 if (root == NULL)<br> 
 { <br>
 cout<<"Tree is empty"<<endl;<br> 
 return;<br> 
 } <br>
 if (ptr != NULL) <br>
 { <br>
 inorder(ptr->left); <br>
 cout<<ptr->info<<" "; <br>
 inorder(ptr->right);<br> 
 } <br>
} <br>
void BST::display(node *ptr, int level)<br> 
{ <br>
 int i; <br>
 if (ptr != NULL) <br>
 { <br>
 display(ptr->right, level+1);<br> 
 cout<<endl; <br>
 if (ptr == root) <br>
 cout<<"Root->: ";<br> 
 else <br>
 { <br>
 for (i = 0;i < level;i++)<br> 
 cout<<" ";<br> 
 } <br>
 cout<<ptr->info; <br>
 display(ptr->left, level+1);<br> 
 } <br>
}<br>

10.Finding minimum and maximum from given unsorted array by using divide conquer method.
#include <iostream><br>
using namespace std;<br>
void MinMax(int arr[], int low, int high, int &min, int &max)<br>
{<br>
if (low == high)<br>
{<br>
if (max < arr[low])<br> {           // comparison 1
max = arr[low];<br>
}<br>

if (min > arr[high]) <br>{          // comparison 2
min = arr[high];<br>
}<br>
return;<br>
}<br>
if (high - low == 1)<br>
{<br>
if (arr[low] < arr[high])<br>
{<br>
if (min > arr[low])<br>
{<br>
min = arr[low];<br>
}<br>
if (max < arr[high])<br>
{<br>
max = arr[high];<br>
}<br>
}<br>
else<br>
{<br>
if (min > arr[high])<br>
{<br>
min = arr[high];<br>
}<br>
if (max < arr[low])<br>
{<br>
max = arr[low];<br>
}<br>
}<br>
return;<br>
}<br>
int mid = (low + high) / 2;<br>
MinMax(arr, low, mid, min, max)<br>;
MinMax(arr, mid + 1, high, min, max<br>);
}<br>
int main()<br>
{<br>
int i, n, arr[50];<br>
cout<<"Enter the number of elements : ";<br>
cin>>n;<br>
for( i = 0; i < n; i++ )<br>
{<br>
cout<<"Enter the element : ";<br>
cin>>arr[i];<br>
}<br>
int max = arr[0], min = arr[0];<br>
MinMax(arr, 0, n - 1, min, max);<br>
cout<<"The minimum array element is "<<min<<endl;<br>
cout<<"The maximum array element is "<<max;<br>
}<br>

9.Write a C++ program for solving the N-Queen’s Problem using backtracking.<br>
#include<iostream><br>
using namespace std;<br>
int grid[10][10];<br>
//print the solution<br>
void print(int n) <br>{<br>
for (int i = 0;i <= n-1; i++) <br>{<br>
for (int j = 0;j <= n-1; j++) <br>{<br>
cout <<grid[i][j]<< " ";<br>
}<br>
cout<<endl;<br>
}<br>
cout<<endl;<br>
cout<<endl;<br>
}<br>
//function for check the position is safe or not
//row is indicates the queen no. and col represents the possible positions
bool isSafe(int col, int row, int n)<br> {<br>
//check for same column<br>
for (int i = 0; i < row; i++)<br> {<br>
if (grid[i][col]) <br>{
return false;<br>
}<br>
}<br>
//check for upper left diagonal
for (int i = row,j = col;i >= 0 && j >= 0; i--,j--)<br> {
if (grid[i][j]) <br>{<br>
return false;<br>
}<br>
}<br>
//check for upper right diagonal
for (int i = row, j = col; i >= 0 && j < n; j++, i--)<br> {
if (grid[i][j]) <br>{<br>
return false;<br>
}<br>
}<br>
return true;<br>
}<br>
//function to find the position for each queen
//row is indicates the queen no. and col represents the possible positions
bool solve (int n, int row) <br>{<br>
if (n == row) <br>{<br>
print(n);<br>
return true;<br>
}<br>
//variable res is use for possible backtracking
bool res = false;<br>
for (int i = 0;i <=n-1;i++)<br> {<br>
if (isSafe(i, row, n)) <br>{
grid[row][i] = 1;<br>
//recursive call solve(n, row+1) for next queen (row+1)
res = solve(n, row+1) || res;//if res ==false then backtracking will occur<br>
//by assigning the grid[row][i] = 0
grid[row][i] = 0;<br>
}<br>
}<br>
return res;<br>
}<br>
int main()<br>
{<br>
ios_base::sync_with_stdio(false);<br>
cin.tie(NULL);<br>
int n;<br>
cout<<"Enter the number of queen"<<endl;<br>
cin >> n;<br>
for (int i = 0;i < n;i++) <br>{
for (int j = 0;j < n;j++) <br>{
grid[i][j] = 0;<br>
}<br>
}<br>
bool res = solve(n, 0);<br>
if(res == false)<br> {<br>
cout << -1 << endl; //if there is no possible solution
}<br> else<br> {<br>
cout << endl;<br>
}<br>
return 0;<br>
}<br>

11.Write a program to implement breadth first search for undirected graph (BFS).<br>
#include<iostream><br>
#include <list><br>
 using namespace std;<br>
 // This class represents a directed graph using<br>
// adjacency list representation<br>
class Graph<br>
{<br>
    int V;    // No. of vertices<br>
 
    // Pointer to an array containing adjacency
    // lists
    list<int> *adj;<br>  
public:<br>
Graph(int V);<br>  // Constructor
  // function to add an edge to graph
void addEdge(int v, int w);<br>
  // prints BFS traversal from a given source s
    void BFS(int s);<br> 
};<br>
 Graph::Graph(int V)<br>
{<br>
    this->V = V;<br>
    adj = new list<int>[V];<br>
}<br>
 void Graph::addEdge(int v, int w)<br>
{<br>
    adj[v].push_back(w); // Add w to v’s list.<br>
}<br>
 void Graph::BFS(int s)<br>
{<br>
    // Mark all the vertices as not visited<br>
    bool *visited = new bool[V];<br>
    for(int i = 0; i < V; i++)<br>
        visited[i] = false;<br>
  // Create a queue for BFS
    list<int> queue;<br>
  // Mark the current node as visited and enqueue it
    visited[s] = true;<br>
    queue.push_back(s);<br>
 // 'i' will be used to get all adja

	
	12.Write a program to implement Min Heap.<br>
 #include<iostream><br>
 #include <conio.h><br>
 using namespace std; <br>
void min_heap(int *a, int m, int n)<br>
{<br>
 int j, t; <br>
t= a[m];<br>
 j = 2 * m;<br>
 while (j <= n)<br>
 { <br>
if (j < n && a[j+1] < a[j])<br>
 j = j + 1;<br>
 if (t < a[j]) <br>
break;<br>
 else <br>
if (t >= a[j])<br>
 {<br>
 a[j/2] = a[j];<br>
 j = 2 * j;<br>
 } <br>
}<br>
 a[j/2] = t; <br>
return;<br>
 } void build_minheap(int *a, int n)<br>
 {<br>
 int k;<br>
 for(k = n/2; k >= 1; k--)<br>
 { <br>
min_heap(a,k,n);<br>
 }<br>
 }<br>
 int main()<br>
 { <br>
int n, i;<br>
 cout<<"enter no of elements of array\n";<br>
 cin>>n;<br>
 int a[30]; <br>
for (i = 1; i <= n; i++)<br>
 {<br>
 cout<<"enter element"<<" "<<(i)<<endl; <br>
cin>>a[i]; <br>
}<br>
 build_minheap(a, n);<br>
 cout<<"Min Heap\n";<br>
 for (i = 1; i <= n; i++) <br>
{ cout<<a[i]<<endl;<br>
 }<br>
 getch();<br>
 }<br>
Output:<br>


	
13.Write a program to implement Max Heap Sort.<br>
#include <iostream><br><br>
using namespace std;<br>
void MaxHeapify (int a[], int i, int n)<br>
{<br>
int j, temp;<br>
temp = a[i];<br>
j = 2*i;<br>
while (j <= n)<br>
{<br>
if (j < n && a[j+1] > a[j])<br>
j = j+1;<br>
if (temp > a[j])<br>
break;<br>
else if (temp <= a[j])<br>
{<br>
a[j/2] = a[j];<br>
j = 2*j;<br>
}<br>
}<br>
a[j/2] = temp;<br>
return;<br>
}<br>
void HeapSort(int a[], int n)<br>
{<br>
int i, temp;<br>
for (i = n; i >= 2; i--)<br>
{<br>
temp = a[i];<br>
a[i] = a[1];<br>
a[1] = temp;<br>
MaxHeapify(a, 1, i - 1);<br>
}<br>
}
void Build_MaxHeap(int a[], int n)<br>
{<br>
int i;<br>
for(i = n/2; i >= 1; i--)<br>
MaxHeapify(a, i, n);<br>
}<br>
int main()<br>
{<br>
int n, i,arr[100];<br>
cout<<"\nEnter the number of data element to be sorted: ";<br>
cin>>n;<br>
n++;<br>
for(i=1;i<n;i++)<br>
{<br>
cout<<"Enter element"<<i<<":";<br>
cin>>arr[i];<br>
}<br>
Build_MaxHeap(arr, n-1);<br>
HeapSort(arr, n-1);<br>
cout<<"\nSorted Data ";<br>
for (i = 1; i < n; i++)<br>
cout<<" "<<arr[i];<br>
return 0;<br>
}<br>
Output:
	

	
	
14.Write a program to insert into an AVL tree and deletion from an AVL tree	
#include<iostream><br>
#include<cstdio><br>
#include<sstream><br>
#include<algorithm><br>
#define pow2(n) (1 << (n))<br>
using namespace std;<br>
struct avl <br>{<br>
   int d;<br>
   struct avl *l;<br>
   struct avl *r;<br>
}*r;<br>
class avl_tree {<br>
   public:<br>
      int height(avl *);<br>
      int difference(avl *);<br>
      avl *rr_rotat(avl *);<br>
      avl *ll_rotat(avl *);<br>
      avl *lr_rotat(avl*);<br>
      avl *rl_rotat(avl *);<br>
      avl * balance(avl *);<br>
      avl * insert(avl*, int);<br>
      void show(avl*, int);<br>
      void inorder(avl *);<br>
      void preorder(avl *);<br>
      void postorder(avl*);<br>
      avl_tree() <br>{<br>
         r = NULL;<br>
      }<br>
};<br>
int avl_tree::height(avl *t)<br> {<br>
   int h = 0;<br>
   if (t != NULL)<br> {<br>
      int l_height = height(t->l);<br>
      int r_height = height(t->r);<br>
      int max_height = max(l_height, r_height);<br>
      h = max_height + 1;<br>
   }<br>
   return h;<br>
}<br>
int avl_tree::difference(avl *t)<br> {<br>
   int l_height = height(t->l);<br>
   int r_height = height(t->r);<br>
   int b_factor = l_height - r_height;<br>
   return b_factor;<br>
}
avl *avl_tree::rr_rotat(avl *parent)<br> {<br>
   avl *t;<br>
   t = parent->r;<br>
   parent->r = t->l;<br><br>
   t->l = parent;<br>
   cout<<"Right-Right Rotation";<br>
   return t;<br>
}<br>
avl *avl_tree::ll_rotat(avl *parent) <br>{<br>
   avl *t;<br>
   t = parent->l;<br>
   parent->l = t->r;<br>
   t->r = parent;<br>
   cout<<"Left-Left Rotation";<br>
   return t;<br>
}<br>
avl *avl_tree::lr_rotat(avl *parent)<br>{<br>
   avl *t;<br>
   t = parent->l;<br>
   parent->l = rr_rotat(t);<br>
   cout<<"Left-Right Rotation";<br>
   return ll_rotat(parent);<br>
}<br>
avl *avl_tree::rl_rotat(avl *parent) {<br>
   avl *t;<br>
   t = parent->r;<br>
   parent->r = ll_rotat(t);<br>
   cout<<"Right-Left Rotation";<br>
   return rr_rotat(parent);<br>
}<br>
avl *avl_tree::balance(avl *t)<br> {<br>
   int bal_factor = difference(t);<br>
   if (bal_factor > 1) {<br>
      if (difference(t->l) > 0)<br>
         t = ll_rotat(t);<br>
      else<br>
         t = lr_rotat(t);<br>
   } else if (bal_factor < -1) <br>{<br>
      if (difference(t->r) > 0)<br>
         t = rl_rotat(t);<br>
      else<br>
         t = rr_rotat(t);<br>
   }<br>
   return t;<br>
}<br>
avl *avl_tree::insert(avl *r, int v)<br> {<br>
   if (r == NULL) <br>{<br>
      r = new avl;<br>
      r->d = v;<br>
      r->l = NULL;<br>
      r->r = NULL;<br>
      return r;<br>
   } else if (v< r->d)<br> {<br>
      r->l = insert(r->l, v);<br>
      r = balance(r);<br>
   } else if (v >= r->d) <br>{<br>
      r->r = insert(r->r, v);<br>
      r = balance(r);<br>
   } return r;<br>
}<br>
void avl_tree::show(avl *p, int l)<br> {<br>
   int i;<br>
   if (p != NULL)<br> {<br>
      show(p->r, l+ 1);<br>
      cout<<" ";<br>
      if (p == r)<br>
         cout << "Root -> ";<br>
      for (i = 0; i < l&& p != r; i++)<br>
         cout << " ";<br>
         cout << p->d;<br>
         show(p->l, l + 1);<br>
   }<br>
}
void avl_tree::inorder(avl *t) <br>{<br>
   if (t == NULL)<br>
      return;<br>
      inorder(t->l);<br>
      cout << t->d << " ";<br>
      inorder(t->r);<br>
}
void avl_tree::preorder(avl *t)<br> {<br>
   if (t == NULL)<br>
      return;<br>
      cout << t->d << " ";<br>
      preorder(t->l);<br>
      preorder(t->r);<br>
}<br>
void avl_tree::postorder(avl *t)<br> {<br>
   if (t == NULL)<br>
      return;<br>
      postorder(t ->l);<br>
      postorder(t ->r);<br>
      cout << t->d << " ";<br>
}<br>
int main() {<br>
   int c, i;<br>
   avl_tree avl;<br>
   while (1) {<br>
<br>
         break;<br>
         case 2:<br>
            if (r == NULL)<br> {
               cout << "Tree is Empty" << endl;<br>
               continue;<br>
            }<br>
            cout << "Balanced AVL Tree:" << endl;<br>
            avl.show(r, 1);<br>
            cout<<endl;<br>
         break;<br>
         case 3:<br>
            cout << "Inorder Traversal:" << endl;<br>
            avl.inorder(r);<br>
            cout << endl;<br>
         break;<br>
         case 4:<br>
            cout << "Preorder Traversal:" << endl;<br>
            avl.preorder(r);<br>
            cout << endl;<br>
         break;<br>
         case 5:<br>
            cout << "Postorder Traversal:" << endl;<br>
            avl.postorder(r);<br>
            cout << endl;<br>
         break;<br>
         case 6:<br>
            exit(1);<br>
         break;<br>
         default:<br>
            cout << "Wrong Choice" << endl;<br>
      }<br>
   }<br>
   return 0;<br>
}<br>

	
	
	
	
	
#include<iostream><br>

using namespace std;

struct node
{
       int key;
       node *parent;
       char color;
       node *left;
       node *right;
};
class RBtree
{
      node *root;
      node *q;
   public :
      RBtree()
      {
              q=NULL;
              root=NULL;
      }
      void insert();
      void insertfix(node *);
      void leftrotate(node *);
      void rightrotate(node *);
      void del();
      node* successor(node *);
      void delfix(node *);
      void disp();
      void display( node *);
      void search();
};
void RBtree::insert()
{
     int z,i=0;
     cout<<"\nEnter key of the node to be inserted: ";
     cin>>z;
     node *p,*q;
     node *t=new node;
     t->key=z;
     t->left=NULL;
     t->right=NULL;
     t->color='r';
     p=root;
     q=NULL;
     if(root==NULL)
     {
           root=t;
           t->parent=NULL;
     }
     else
     {
         while(p!=NULL)
         {
              q=p;
              if(p->key<t->key)
                  p=p->right;
              else
                  p=p->left;
         }
         t->parent=q;
         if(q->key<t->key)
              q->right=t;
         else
              q->left=t;
     }
     insertfix(t);
}
void RBtree::insertfix(node *t)
{
     node *u;
     if(root==t)
     {
         t->color='b';
         return;
     }
     while(t->parent!=NULL&&t->parent->color=='r')
     {
           node *g=t->parent->parent;
           if(g->left==t->parent)
           {
                        if(g->right!=NULL)
                        {
                              u=g->right;
                              if(u->color=='r')
                              {
                                   t->parent->color='b';
                                   u->color='b';
                                   g->color='r';
                                   t=g;
                              }
                        }
                        else
                        {
                            if(t->parent->right==t)
                            {
                                 t=t->parent;
                                 leftrotate(t);
                            }
                            t->parent->color='b';
                            g->color='r';
                            rightrotate(g);
                        }
           }
           else
           {
                        if(g->left!=NULL)
                        {
                             u=g->left;
                             if(u->color=='r')
                             {
                                  t->parent->color='b';
                                  u->color='b';
                                  g->color='r';
                                  t=g;
                             }
                        }
                        else
                        {
                            if(t->parent->left==t)
                            {
                                   t=t->parent;
                                   rightrotate(t);
                            }
                            t->parent->color='b';
                            g->color='r';
                            leftrotate(g);
                        }
           }
           root->color='b';
     }
}

void RBtree::del()
{
     if(root==NULL)
     {
           cout<<"\nEmpty Tree." ;
           return ;
     }
     int x;
     cout<<"\nEnter the key of the node to be deleted: ";
     cin>>x;
     node *p;
     p=root;
     node *y=NULL;
     node *q=NULL;
     int found=0;
     while(p!=NULL&&found==0)
     {
           if(p->key==x)
               found=1;
           if(found==0)
           {
                 if(p->key<x)
                    p=p->right;
                 else
                    p=p->left;
           }
     }
     if(found==0)
     {
            cout<<"\nElement Not Found.";
            return ;
     }
     else
     {
         cout<<"\nDeleted Element: "<<p->key;
         cout<<"\nColour: ";
         if(p->color=='b')
     cout<<"Black\n";
    else
     cout<<"Red\n";

         if(p->parent!=NULL)
               cout<<"\nParent: "<<p->parent->key;
         else
               cout<<"\nThere is no parent of the node.  ";
         if(p->right!=NULL)
               cout<<"\nRight Child: "<<p->right->key;
         else
               cout<<"\nThere is no right child of the node.  ";
         if(p->left!=NULL)
               cout<<"\nLeft Child: "<<p->left->key;
         else
               cout<<"\nThere is no left child of the node.  ";
         cout<<"\nNode Deleted.";
         if(p->left==NULL||p->right==NULL)
              y=p;
         else
              y=successor(p);
         if(y->left!=NULL)
              q=y->left;
         else
         {
              if(y->right!=NULL)
                   q=y->right;
              else
                   q=NULL;
         }
         if(q!=NULL)
              q->parent=y->parent;
         if(y->parent==NULL)
              root=q;
         else
         {
             if(y==y->parent->left)
                y->parent->left=q;
             else
                y->parent->right=q;
         }
         if(y!=p)
         {
             p->color=y->color;
             p->key=y->key;
         }
         if(y->color=='b')
             delfix(q);
     }
}

void RBtree::delfix(node *p)
{
    node *s;
    while(p!=root&&p->color=='b')
    {
          if(p->parent->left==p)
          {
                  s=p->parent->right;
                  if(s->color=='r')
                  {
                         s->color='b';
                         p->parent->color='r';
                         leftrotate(p->parent);
                         s=p->parent->right;
                  }
                  if(s->right->color=='b'&&s->left->color=='b')
                  {
                         s->color='r';
                         p=p->parent;
                  }
                  else
                  {
                      if(s->right->color=='b')
                      {
                             s->left->color=='b';
                             s->color='r';
                             rightrotate(s);
                             s=p->parent->right;
                      }
                      s->color=p->parent->color;
                      p->parent->color='b';
                      s->right->color='b';
                      leftrotate(p->parent);
                      p=root;
                  }
          }
          else
          {
                  s=p->parent->left;
                  if(s->color=='r')
                  {
                        s->color='b';
                        p->parent->color='r';
                        rightrotate(p->parent);
                        s=p->parent->left;
                  }
                  if(s->left->color=='b'&&s->right->color=='b')
                  {
                        s->color='r';
                        p=p->parent;
                  }
                  else
                  {
                        if(s->left->color=='b')
                        {
                              s->right->color='b';
                              s->color='r';
                              leftrotate(s);
                              s=p->parent->left;
                        }
                        s->color=p->parent->color;
                        p->parent->color='b';
                        s->left->color='b';
                        rightrotate(p->parent);
                        p=root;
                  }
          }
       p->color='b';
       root->color='b';
    }
}

void RBtree::leftrotate(node *p)
{
     if(p->right==NULL)
           return ;
     else
     {
           node *y=p->right;
           if(y->left!=NULL)
           {
                  p->right=y->left;
                  y->left->parent=p;
           }
           else
                  p->right=NULL;
           if(p->parent!=NULL)
                y->parent=p->parent;
           if(p->parent==NULL)
                root=y;
           else
           {
               if(p==p->parent->left)
                       p->parent->left=y;
               else
                       p->parent->right=y;
           }
           y->left=p;
           p->parent=y;
     }
}
void RBtree::rightrotate(node *p)
{
     if(p->left==NULL)
          return ;
     else
     {
         node *y=p->left;
         if(y->right!=NULL)
         {
                  p->left=y->right;
                  y->right->parent=p;
         }
         else
                 p->left=NULL;
         if(p->parent!=NULL)
                 y->parent=p->parent;
         if(p->parent==NULL)
               root=y;
         else
         {
             if(p==p->parent->left)
                   p->parent->left=y;
             else
                   p->parent->right=y;
         }
         y->right=p;
         p->parent=y;
     }
}

node* RBtree::successor(node *p)
{
      node *y=NULL;
     if(p->left!=NULL)
     {
         y=p->left;
         while(y->right!=NULL)
              y=y->right;
     }
     else
     {
         y=p->right;
         while(y->left!=NULL)
              y=y->left;
     }
     return y;
}

void RBtree::disp()
{
     display(root);
}
void RBtree::display(node *p)
{
     if(root==NULL)
     {
          cout<<"\nEmpty Tree.";
          return ;
     }
     if(p!=NULL)
     {
                cout<<"\n\t NODE: ";
                cout<<"\n Key: "<<p->key;
                cout<<"\n Colour: ";
    if(p->color=='b')
     cout<<"Black";
    else
     cout<<"Red";
                if(p->parent!=NULL)
                       cout<<"\n Parent: "<<p->parent->key;
                else
                       cout<<"\n There is no parent of the node.  ";
                if(p->right!=NULL)
                       cout<<"\n Right Child: "<<p->right->key;
                else
                       cout<<"\n There is no right child of the node.  ";
                if(p->left!=NULL)
                       cout<<"\n Left Child: "<<p->left->key;
                else
                       cout<<"\n There is no left child of the node.  ";
                cout<<endl;
    if(p->left)
    {
                 cout<<"\n\nLeft:\n";
     display(p->left);
    }
    /*else
     cout<<"\nNo Left Child.\n";*/
    if(p->right)
    {
     cout<<"\n\nRight:\n";
                 display(p->right);
    }
    /*else
     cout<<"\nNo Right Child.\n"*/
     }
}
void RBtree::search()
{
     if(root==NULL)
     {
           cout<<"\nEmpty Tree\n" ;
           return  ;
     }
     int x;
     cout<<"\n Enter key of the node to be searched: ";
     cin>>x;
     node *p=root;
     int found=0;
     while(p!=NULL&& found==0)
     {
            if(p->key==x)
                found=1;
            if(found==0)
            {
                 if(p->key<x)
                      p=p->right;
                 else
                      p=p->left;
            }
     }
     if(found==0)
          cout<<"\nElement Not Found.";
     else
     {
                cout<<"\n\t FOUND NODE: ";
                cout<<"\n Key: "<<p->key;
                cout<<"\n Colour: ";
    if(p->color=='b')
     cout<<"Black";
    else
     cout<<"Red";
                if(p->parent!=NULL)
                       cout<<"\n Parent: "<<p->parent->key;
                else
                       cout<<"\n There is no parent of the node.  ";
                if(p->right!=NULL)
                       cout<<"\n Right Child: "<<p->right->key;
                else
                       cout<<"\n There is no right child of the node.  ";
                if(p->left!=NULL)
                       cout<<"\n Left Child: "<<p->left->key;
                else
                       cout<<"\n There is no left child of the node.  ";
                cout<<endl;

     }
}
int main()
{
    int ch,y=0;
    RBtree obj;
    do
    {
                cout<<"\n\t RED BLACK TREE " ;
                cout<<"\n 1. Insert in the tree ";
                cout<<"\n 2. Delete a node from the tree";
                cout<<"\n 3. Search for an element in the tree";
                cout<<"\n 4. Display the tree ";
                cout<<"\n 5. Exit " ;
                cout<<"\nEnter Your Choice: ";
                cin>>ch;
                switch(ch)
                {
                          case 1 : obj.insert();
                                   cout<<"\nNode Inserted.\n";
                                   break;
                          case 2 : obj.del();
                                   break;
                          case 3 : obj.search();
                                   break;
                          case 4 : obj.disp();
                                   break;
                          case 5 : y=1;
                                   break;
                          default : cout<<"\nEnter a Valid Choice.";
                }
                cout<<endl;

    }while(y!=1);
    return 1;
}
