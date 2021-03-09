# Interview Questions:

**1. Added node in sorted list**
```

typedef struct node {
	struct node *next;
	int data;
} node_t;


node_t *add_node(node_t *head, int data)
{
	node_t *new = NULL;
	node_t *ptr = NULL;

	new = malloc(sizeof *node);
	if (new == NULL) {
		perror("malloc failed");
		return NULL;
	}

	new->next = NULL;
	new->data = data;

	if (head == NULL) {
		head = new;
		return head;
	}


	ptr = head;

	while(ptr != NULL) {
		if (new->data > ptr->data) {
			ptr->next = new;
		} else if () {
			
		}

	}

}
```

**Single Linked List add the node & insert the node in 1st, middle, last and position based sample programs** <br>

```

			temp->next=new;
		}
	}
}
void insert_first(int value)
{

	struct singly *new=NULL;
	new =(struct singly *)malloc (sizeof(struct singly));
	new->data =value;
	new->next =head;
	head =new;
}
void insert_last(int value)
{

	struct singly *temp=NULL;
	struct singly *new=NULL;
	temp =head;
	while(temp->next!=NULL)
	{
		temp =temp->next;
	}
	new =(struct singly *)malloc (sizeof(struct singly));
	new->data =value;
	new->next =NULL;
	temp->next =new;
}
void insert_middle(int value)
{

	struct singly *temp=NULL;
	struct singly *new=NULL;
	int count =0,posi=0;
	temp =head;
	while(temp->next!=NULL)
	{
		count++;
		temp =temp->next;
	}
	count=count/2;
	temp =head;
	while(temp->next!=NULL)
	{
		temp =temp->next;
		posi++;
		if(count==posi)
		{

			new =(struct singly *)malloc (sizeof(struct singly));
			new->data =value;
			new->next =temp->next;
			temp->next =new;
		}
	}
}
void insert_position(int value)
{
 struct singly *temp=NULL;
	struct singly *new=NULL;
	int count =0,posi=0;
	printf("enter the position");
	scanf("%d",&posi);
	temp =head;
	while(temp->next!=NULL)
	{
		temp =temp->next;
		count++;
		if(count==posi)
		{

			new =(struct singly *)malloc (sizeof(struct singly));
			new->data =value;
			new->next =temp->next;
			temp->next =new;
		}
	}
}
void display()
{
	struct singly *temp =NULL;
	temp=head;
	while(temp!=NULL)
	{
		printf("%d->",temp->data);
		temp=temp->next;

	}
	printf("NULL");
}

void main()
{
	create(10);
	create(20);
	create(30);
	insert_first(100);
	insert_last(300);
	insert_middle(200);
	insert_position(400);
	display();
}

```

**Find the duplicate in Single linked list** <br>
```
#include<stdio.h>
#include<stdlib.h>
struct get{
	int data;
	struct get *next;
};
struct get *h=NULL;
struct get *head1=NULL;
void create (int value)
{
	struct get *temp = NULL;
	struct get *new = NULL;

	if (h==NULL)
	{
		h = (struct get *)malloc (sizeof(struct get));
		if (h==NULL)
		{
			printf ("memory allocation failed");
			return;
		}
		else
		{
			h->data = value;
			h->next = NULL;
		}
	}
	else
	{
		temp = h;
		while(temp->next!=NULL)
		{
			temp =temp->next ;
		}
		new = (struct get *)malloc (sizeof(struct get));
		new->data = value;
		new->next = NULL;
		temp->next = new;
	}

}
void sorting ()
{

	struct get *temp = NULL;
	struct get *new = NULL;
	int s;
	temp =h;
	while (temp!=NULL)
	{
		new = temp->next;
		while (new!=NULL)
		{
			if (temp->data > new->data)
			{
				s = temp->data;
				temp->data=new->data;
				new->data=s;
			}
			new=new->next;
		}
		temp= temp->next;
	}
}
void duplicate ()
{

	struct get *temp = NULL;
	struct get *new = NULL;
	struct get *s = NULL;
	struct get *b = NULL;
	int count =0;
	temp =h;
	//new = temp->next;
	while (temp!=NULL)
	{
		new = temp->next;
		while (new!=NULL)
		{
			if (temp->data ==  new->data)
			{
//				printf ("%d %d",temp->data,new->data);
				s = new->next;
				free (new);
				new = s;
//				printf (" %d ",temp->data);

			}
			else
			{
				new= new->next;
			}
		}
		temp=temp->next;
	}
}
void display ()
{

	struct get *temp = NULL;
	int count =0,pos=0;
	temp = h;
	while(temp!=NULL)
	{
		printf("%d->",temp->data);

		temp = temp->next;
	}
	printf("NULL");
}
void main()
{
	create(60);
	create(20);
	create(30);
	create(70);
	create(50);
	create(10);
	sorting ();
	duplicate();
	display();
}
```
**2. Reversing doubly linked list**
```
typedef struct node {
	struct node *next;
	int data;
} node_t;

int reverse(node_t *head)
{
	node_t *ptr = NULL;

	if (head == NULL) {
		return -1;
	}

	ptr = head;	

	while(ptr != NULL) {
		if (ptr->next != NULL) {
			next = ptr->next;
			prev = ptr->prev;
			ptr->next = prev;
			ptr->prev = next;
		}
		ptr = next
	}
}
```
**3. What is dangling pointer?** <br>
A pointer pointing to a memory location that has been deleted (or freed) is called dangling pointer.

```

int a;
static int b;

int main()
{
	static int c;
	char *ptr = (char *)malloc(10);

	free(ptr);

	ptr ///
}
```

what if dest mac is not match in switch and router ?<br>
fragmentation in ip stack ?<br>
what if frame exceeds the mtu size ?<br>
	if fragmentation enable, the frame get fragment<br>
max port no ?<br>
can we set own client port no ?<br>
what listen will do ?<br>
	monitor incomming req and create passive sockets<br>
How global values are acceseddd in parent and child ?<br>
how mutex values in acccess by two process (bcz two procs are not communicate) ?<br>
is static varible with same name is cause compilation error ?<br>
when global variables get resolve ?<br>
need of volatile with compiler flag O0 ?<br>
	need to remove optimization for specific variable<br>
memory barrier in kernel<br>
net filters<br>
TCP handshake<br>
packet lifecycle<br>
how stp select root node ? based on mac addr<br>
diff snmp walk and bulk walk<br>
trap and alram<br>
need of makefile<br>


set 0 to diagnal elements in multi-dimension matrix
```
int nullit(int arr[][], size_t size)
{
	int i = 0;
	int j = 0;
	
	for(i = 0; i < size; i++) {
		for (j = 0; j < size; j++) {
			if ((i == j) || ((i == 0) && (j == size -1)) || ((i == size - 1) && (j = 0)) {
				arr[i][j] = 0;
			}
		}
	}
}

will work only for 3x3
```

remove node only with node pointer. (no reference to head pointer)
memory segment

List program
```
take ll reverse 

a b c d e f g h
a h c f e d g b

___ func()

int func (struct node *list)
{
    int i = 0, j = 0;
    struct node *current = NULL;
    strcu node *end = NULL;
    
    if (list == NULL) {
        return -1; //null head
    }

    current = list;
  
    while(current != NULL) {
        current = current->next;
    }
   
    end = current; //points end node
    
    current = list; //resetting first node
	
    while (current != NULL) {
        if (current->next != NULL) {
            new = end;
            end->prev->next = current->next;
			if (end->prev->prev != NULL) {
				end = end->prev->prev;
			}	
            new->next = current->next->next;
            new->prev = current;
            current->next = new;
            
            if (current->next->next != NULL) {
				current = current->next->next;
			}
        }
    }
	
	return 0;
}
```
What are all the restrictions for writing the kernel modules?<br>
	could not use printf, malloc will use kprintf and kmalloc<br>
How host know its IP?<br>
How router know its own packets becuase it does not have routing table for that.<br>
how vlagrind reports memory leak and how it know?<br>
how malloc works and its memory header?<br>
What symbol table consists?<br>
what is ELF and what it consists?<br>
What is best data-structure to maintain routing table?<br>
Type of IPC<br>
Diff of Socket and Shared Memory<br>
Ethernet field<br>
Swap bit from x to y<br>
```
num = 1011101110111011
ans   1011111111111011

mask = 111111111111111
a = 111111111111000
b = 111110000000000
mask = a^b = 0000001111111000
ans = num | mask
ans   1011111111111011
```
Remove duplicates in a list: 
- dont use loop
- can use merge sort to remove dups (not suitable for the list does not require sorting)
- can use hashing
```
1-->2-->2-->3
1-->2-->3

1-->1-->2-->3-->2
1-->2-->3

struct node {
    struct node *next;
    int data;
};

int remove_dups(struct node *list)
{
    int retavl = -1;
    struct node *curr = NULL;
    struct node *next = NULL;
    struct node *tmp = NULL;
    
    do {
        if (list == NULL) {
            fprintf(stderr, "list is null\n");
            retval = -1;
            break; 
        }

        while(curr != NULL) {
            curr = list;
            next = curr->next;

            while(next != NULL) {
                if (curr->data == next->data) {
                    //remove duplicate node
                    curr->next = next->next;
                    free(
                }
            }
        }

        if (curr->next == NULL) {
            /* list has only one element. and no duplicates. */
            fprintf(stderr, "only one element\n");
            retval = 0;
            break; 
        } else {
            next =

        }
    } while(0);

    return retval;
}
```
Where the shared memory will create memory?<br>
--user space memory in file system as a file.<br>
How to create the new process?<br>
--- fork and exec<br>
Diff process and threads.<br>
Ret val of fork()<br>
How to insert a new module in kernel?<br>
--- insmod and modprobe<br>
What are the fields will change in a packet from Router to switch?<br>
---Source and dest MAC, Checksum and TTL.<br>
Program to return array of structure and how to chk the return value?<br>
Output of below code 
```
int *ptr=NULL;
ptr=ptr+1;
printf("%d\n",ptr);
```
Ahow to access the a[2][2] in pointer method in below array?<br>
```
123
456
789
```
Memory layouts<br>
Use of static variables<br>
Where the memory is allocated for Extern variable<br>
Type of sockets?<br>
---Sytream(TCP) and Datagram(UDP) and also we have Raw socket (ICMP)<br>
What is deadlock<br>

Output of below code:<br>
```
main()
{
    const int q = 5;
    int const* p = &q; 

    *p = 7;
    printf ("%d", *p);        
    
    return 0;
 }
```
Program for below matric<br>
```
1
1 1
1 2 1
1 3 3 1
1 4 6 4 1
1 5 10 10 5 1
```
Memory pattern of little endian and big endian<br>
List to check palindrom<br>
```

NULL <-- 1 <--> 0 <--> 1 <--> 0 <--> 1 --> NULL

2 1 2 2 1
    1 2 3


fun(struct node *list)
{
	strcut node *tmp = NULL;
	strcut node *last = NULL;

	if (list == NULL) {
		return -1; //empty list
	}

	tmp = list;
	while(tmp->next != NULL) {
		tmp = tmp->next;
	}

	last = tmp;
	tmp = list;

	while(tmp != NULL) {
		if (tmp->data != last->data) {
			return -1; // list is not a palindrome
		}
		tmp = tmp->next;
		last = last->prev;
	}

	return 0;
}
```
Consequtive dynamic allocation for multi-dimension array
```
struct node {
	struct node *next;
	struct node *prev;
	int data;
};

int main()
{
	//char a[2][5];

	char **b = NULL;
	int r = 2; c = 5;

	b = (char **)malloc(size);
	if (b == NULL) {
		perror("malloc failed");
		return -1;
	}

	while(i < r) {
		b[i] = malloc(c * sizeof (**b));
		if (b[i] == NULL) {
			perror("malloc failed");
			return -1;
		}
		i++;
	}
}
```
Ethernet frame fields<br>
Packet travel between  ```host -- switch --- host``` and ```host --- router --- host```.

**How does free() know the size of memory to be deallocated?**<br>
When memory allocation is done, the actual heap space allocated is one word larger than the requested memory.<br> 
The extra word is used to store the size of the allocation and is later used by free( ).

MAC learning<br>
size of below strcuture
```
strcut iphdr {
	unsingned int version:3;
}
```
2D Array implementation<br>
Traverse a node in BFS tree<br>
```
        10
    4       23
1      7  12    27

1. Traverse and add the elements in Q
10, 4, 23, 1, 7, 12, 27 

2. Print the elements
    10,
 4     23
 ```
Write a strcutre for IP packet<br>
Set bits as per the passed petterns<br>
```
"1-2, 10-12"
"10-12, 15, 18-20"


int val;

int set_bit_range(char *range)
{
	char *tok = NULL;
	char *saveptr = NULL;
	
	tok = strtok_r(patter, "-", &saveptr);
	while(tok != NULL) {
		pos = atoi(tok);
		val = val | ( 1 << pos - 1);
		tok = strtok_r(NULL, "-", &saveptr);
	}
	
	return 0;
}


int parse_and_setbit(char *pattern)
{
	char *tok = NULL;
	char *saveptr = NULL;
	
	if (pattern == NULL) {
		fprintf(stderr, "invalid pattern !\n");
		return -1;
	}

	tok = strtok_r(patter, ",", &saveptr);
	if (tok != NULL) {
		retval = set_range(tok);
		tok = strtok_r(NULL, ",", &saveptr);
	}

}
```
Set Nth bit<br>
```
int setbit(unsigned int val, unsigned int pos)
{
	int num = 0;
	
	if ((val < 0) || (pos <= 0)) {
		return -1; //Error
	}

	num = val | (1 << (pos - 1));
	
	return num;
	
}
```
Print Endieness<br>
```
int print_endienes(void)
{
	int *a = 1;
	
	if ((char *)a == 0) {
		printf("Little endian");
	} else {
		printf("Big endian");
	}
}
```

Count set bits<br>
```
int count_setbits(int val) {
	int nbit = 0, i = 0;
	int size = sizeof(val);
	
	while(i < (size * 8)) {
		val = (val & ( 1 << i ));
		if (val) {
			nbit++;
		}
		
		if (val == 0) {
			break;
		}
		
		i++;
	}
	
	return nbit;
}
```

STRREV:
```



str = "hello"

char *strrev(char *str)
{
	char tmp = (char) 0;
	char *st = NULL;
	char *end = NULL;
	
	if (str == NULL) {
		return NULL;
	}

	st = end = str;

	while (end != '\0') {
		end++;
	}

	end--;

	while(st < end) {
		tmp = *end;
		end = *st;
		st = tmp;
		
		st++;
		end--;
	}
	
	return str;
}
```
Diff AVL and Binary tree<br>
Expression check
```
#define MAX_SIZE 32
int experchk(char *data)
{
	char *ptr = NULL;
	char stack[MAX_SIZE] = {0};
	int sp = 0;

	ptr = data;
	while(*ptr != '\0') {
		switch (*ptr) {
			case '(': case '{': case '[':
				//Push operation
				stack[sp] = *ptr;
				sp++;
				break;

			case ')':
				--sp;
				if (stack[sp] != '(') {
					fprintf(stderr, "Invalid expression !\n");
					return -1;
				}
				stack[sp] = 0;
				break;
 
			case ']':
				--sp;
				if (stack[sp] != ']') {
					fprintf(stderr, "Invalid expression !\n");
					return -1;
				}
				stack[sp] = 0;
				break;

 			case '}':
				--sp;
				if (stack[sp] != '{') {
					fprintf(stderr, "Invalid expression !\n");
					return -1;
				}
				stack[sp] = 0;
				break;
		}
		ptr++;
	}

	return retval;
}
```

List program
```
8 1 3 
9 1 2 
7 3 5

typecast struct node {
	strcut node *next;
	int data;
} node_t;


//Returning new list
node_t add_list_element(node_t *list1, node_t *list2)
{
	node_t *l1 = NULL;
	node_t *l2 = NULL;
	node_t *newlist = NULL;
	node_t *new = NULL;

	if ((list1 == NULL) || (list2 == NULL)) {
		fprintf(stderr, "invalid list !");
		return -1;
	}

	l1 = list1;
	l2 = list1;

	while((l1 != NULL) && (l2 != NULL)) {
		//Creating new list node
		new = (node_t *)malloc(sizeof(*new));
		if (new == NULL) {
			perror("malloc failed for new node");
			return -1;
		}

		if (newlist == NULL) {
			newlist = new;
			prev = NULL;
		}

		new->next = prev;
		new->data = (l1->data + l2->data);

		l1 = l1->next;
		l2 = l2->next;
	}

	return newlist;
}
```
