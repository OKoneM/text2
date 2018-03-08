Node *TailInsert(Node *pNode){  
  
    Node *pInsert; //要插入的节点  
    Node *pMove; //遍历链表的节点  
    pInsert = (Node*)malloc(sizeof(Node));  
    if (pInsert == NULL)
	{  
        printf("%s函数执行，内存分配失败，建立链表失败\n",__FUNCTION__);  
        return NULL;  
    }  
  
    memset(pInsert, 0, sizeof(Node));  
    scanf("%d",&(pInsert->element));  
    pInsert->next = NULL;  
  
    if (pInsert->element <= 0) {  
        printf("%s函数执行，输入数据有误，建立链表失败\n",__FUNCTION__);  
        return NULL;  
    }  
  
    pMove = pNode;  
    while (pInsert->element > 0)
	{  
        if (pNode == NULL) 
		{  
            //注意不要忘了修改pMove指针的指向，初始pMove一定要指向头节点  
            pNode = pInsert;  
            pMove = pNode;  
        }
		else
		{  
            //遍历找到最后一个节点  
            while (pMove->next != NULL)
			{  
                pMove = pMove->next;  
            }  
            pMove->next = pInsert;  
        }  
  
        pInsert = (Node*)malloc(sizeof(Node));  
        if (pInsert == NULL) 
		{  
            printf("%s函数执行，内存分配失败，建立链表失败\n",__FUNCTION__);  
            return NULL;  
        }  
  
        memset(pInsert, 0, sizeof(Node));  
        scanf("%d",&(pInsert->element));  
        pInsert->next = NULL;  
    }  
  
    printf("%s函数执行，尾插法建立链表成功\n",__FUNCTION__);  
  
    return pNode;  
}  
