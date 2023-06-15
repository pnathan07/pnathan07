Module Module1
    Function verification(ByVal x As String) As String
        Dim a As String = x
        While True
            If a = "yes" Or a = "Yes" Or a = "YES" Then
                Exit While
            ElseIf a = "no" Or a = "No" Or a = "NO" Then
                Exit While
            Else
                Console.WriteLine()
                Console.WriteLine("Error! please try again, is there an error in your data?")
                Console.WriteLine("yes/no")
                a = Console.ReadLine()
            End If
        End While
        Return a
    End Function
    Function verification2(ByVal x As String) As String
        Dim B As String = x
        While True
            If B = "name" Or B = "Name" Or B = "NAME" Then
                Exit While
            ElseIf B = "phone" Or B = "Phone" Or B = "PHONE" Then
                Exit While
            ElseIf B = "Id" Or B = "id" Or B = "ID" Then
                Exit While
            Else
                Console.WriteLine()
                Console.WriteLine("Answer not in the system")
                Console.WriteLine("What would you like to change ?")
                Console.WriteLine("Name/Phone/Id")
                B = Console.ReadLine()
            End If
        End While
        Return B
    End Function
    Function verification3(ByVal x As String) As String
        Dim a As String = x
        While True
            If a = "brioche" Or a = "BRIOCHE" Or a = "BRIOCHE" Then
                a = "brioche"
                Exit While
            ElseIf a = "flan" Or a = "Flan" Or a = "FLAN" Then
                a = "flan"
            ElseIf a = "fraisier" Or a = "FRAISIER" Or a =
            "Fraisier" Then
                a = "fraisier"
                Exit While
            Else
                Console.WriteLine()
                Console.WriteLine("Error! please try again, is there an error in your data?")
                Console.WriteLine("please write your word well, thank you !")
                Console.WriteLine("brioche/flan/fraisier")
                Console.WriteLine()
                a = Console.ReadLine()
                Console.WriteLine()
            End If
        End While
        Return a
    End Function
    Class donne_client
        Dim name, phone, taz As String
        'entree de donnees
        Sub New()
            Console.WriteLine()
            Console.WriteLine(" Please enter your client's name :")
            name = (Console.ReadLine())
            Console.WriteLine()
            Console.WriteLine("Thanks " & name)
            Console.WriteLine("now please enter your client's cell phone number :")
            phone = (Console.ReadLine())
            Console.WriteLine()
            Console.WriteLine("Thanks " & name)
            Console.WriteLine("now please enter your client's id :")
            taz = Console.ReadLine()
            Console.WriteLine()
            Console.WriteLine("Thanks " & name & " here the summary of your data.")
            Console.WriteLine(" Name : " & name)
            Console.WriteLine(" phone : " & phone)
            Console.WriteLine(" Id : " & taz)

        End Sub
        Sub get_print()
            Console.WriteLine()
            Console.WriteLine("name : " & name)
            Console.WriteLine("phone : " & phone)
            Console.WriteLine("Id : " & taz)
        End Sub
        Sub set_datachange()
            Dim A As String
            Console.WriteLine()
            Console.WriteLine("Is there an error in your data ? ")
            Console.WriteLine("yes/no")
            A = verification(Console.ReadLine())
            While A = "yes" Or A = "YES" Or A = "Yes"
                Console.WriteLine()
                Console.WriteLine("What would you like to change ?")
                Console.WriteLine("name/phone/Id")
                Dim B As String = verification2(Console.ReadLine())
                If B = "name" Or B = "Name" Or B = "NAME" Then
                    Console.WriteLine()
                    Console.WriteLine("Please enter your client's name again :")
                    name = (Console.ReadLine())
                ElseIf B = "phone" Or B = "Phone" Or B = "PHONE" Then
                    Console.WriteLine()
                    Console.WriteLine("please enter your phone number again :")
                    phone = CInt(Console.ReadLine())
                ElseIf B = "Id" Or B = "id" Or B = "ID" Then
                    Console.WriteLine()
                    Console.WriteLine("please enter your Id again :")
                    taz = Console.ReadLine()
                End If
                Console.WriteLine()
                Console.WriteLine("Would you like to see your data again ?")
                Console.WriteLine("yes/no")
                Dim C As String = verification(Console.ReadLine())
                If C = "yes" Or C = "Yes" Or C = "YES" Then
                    get_print()
                End If
                Console.WriteLine()
                Console.WriteLine("Would you like to change your data again ?")
                Console.WriteLine("yes/no")
                A = verification(Console.ReadLine())
            End While
        End Sub
        Sub Print()
            Console.WriteLine("name {0}, phone {1}, Id {2} ", name,
            phone, taz)
        End Sub
        Function get_name() As String
            Return name
        End Function
    End Class
    Class brioche
        Dim oeufs_brioche, farine_brioche, sucre_brioche, cout_horraire_brioche As Integer
        Dim nb_brioche As Integer
        Sub New(ByVal n As Integer)
            nb_brioche = n
        End Sub
        Sub set_brioche(ByVal n As Integer)
            nb_brioche = n
        End Sub
        Function get_nb_brioche() As Integer
            Return nb_brioche
        End Function
        Function get_cout_horraire_brioche() As Integer
            If nb_brioche > 0 Then
                cout_horraire_brioche = (67.5 + (2 * nb_brioche)) / nb_brioche
            Else
                cout_horraire_brioche = 0
            End If
            Return cout_horraire_brioche
        End Function
        Function get_oeufs_brioche() As Integer
            oeufs_brioche = 1 * nb_brioche
            Return oeufs_brioche
        End Function
        Function get_farine_brioche() As Integer
            farine_brioche = 90 * nb_brioche
            Return farine_brioche
        End Function
        Function get_sucre_brioche() As Integer
            sucre_brioche = 10 * nb_brioche
            Return sucre_brioche
        End Function
        Function get_prix_oeufs_brioche() As Integer
            Return 1 * nb_brioche
        End Function
        Function get_prix_farine_brioche(ByVal n As Integer) As Integer
            Return (n / 1000) * 3 * nb_brioche
        End Function
        Function get_prix_sucre_brioche(ByVal n As Integer) As Integer
            Return (n / 1000) * 4 * nb_brioche
        End Function
    End Class
    Class flan
        Dim oeufs_flan, farine_flan, sucre_flan, cout_horraire_flan As Integer
        Dim nb_flan As Integer
        Sub New(ByVal n As Integer)
            nb_flan = n
        End Sub
        Sub set_flan(ByVal n As Integer)
            nb_flan = n
        End Sub
        Function get_nb_flan() As Integer
            Return nb_flan
        End Function
        Function get_cout_horraire_flan() As Integer
            If nb_flan > 0 Then
                cout_horraire_flan = (45 + 5 * nb_flan) / nb_flan
            Else
                cout_horraire_flan = 0
            End If
            Return cout_horraire_flan
        End Function
        Function get_oeufs_flan() As Integer
            oeufs_flan = 1 * nb_flan
            Return oeufs_flan
        End Function
        Function get_farine_flan() As Integer
            farine_flan = 15 * nb_flan
            Return farine_flan
        End Function
        Function get_sucre_flan() As Integer
            sucre_flan = 12 * nb_flan
            Return sucre_flan
        End Function
        Function get_prix_oeufs_flan(ByVal n As Integer) As Integer
            Dim prix As Integer = 1 * n
            Return prix
        End Function
        Function get_prix_farine_flan(ByVal n As Integer) As Integer
            Dim prix As Integer = (n / 1000) * 3 * nb_flan
            Return prix
        End Function
        Function get_prix_sucre_flan(ByVal n As Integer) As Integer
            Dim prix As Integer = (n / 1000) * 4 * nb_flan
            Return prix
        End Function
    End Class
    Class fraisier
        Dim oeufs_fraisier, farine_fraisier, sucre_fraisier, cout_horraire_fraisier As Integer
        Dim nb_fraisier As Integer
        Sub New(ByVal n As Integer)
            nb_fraisier = n
        End Sub
        Sub set_fraisier(ByVal n As Integer)
            nb_fraisier = n
        End Sub
        Function get_nb_fraisier() As Integer
            Return nb_fraisier
        End Function
        Function get_cout_horraire_fraisier() As Integer
            If nb_fraisier > 0 Then
                cout_horraire_fraisier = (7.5 + 7 * nb_fraisier) /
                nb_fraisier
            Else
                cout_horraire_fraisier = 0
            End If
            Return cout_horraire_fraisier
        End Function
        Function get_oeufs_fraisier() As Integer
            oeufs_fraisier = 2 * nb_fraisier
            Return oeufs_fraisier
        End Function
        Function get_farine_fraisier() As Integer
            farine_fraisier = 0 * nb_fraisier
            Return farine_fraisier
        End Function
        Function get_sucre_fraisier() As Integer
            sucre_fraisier = 25 * nb_fraisier
            Return sucre_fraisier
        End Function
        Function get_prix_oeufs_fraisier(ByVal n As Integer) As Integer
            Dim prix As Integer = 1 * n
            Return prix
        End Function
        Function get_prix_farine_fraisier(ByVal n As Integer) As Integer
            Dim prix As Integer = (n / 1000) * 3 * nb_fraisier
            Return prix
        End Function
        Function get_prix_sucre_fraisier(ByVal n As Integer) As Integer
            Dim prix As Integer = (n / 1000) * 4 * nb_fraisier
            Return prix
        End Function
    End Class
    Function price(ByVal o As Integer, ByVal f As Integer, ByVal s As Integer, ByVal t As Integer)
        Dim sum As Integer = (o + f + s + t)
        Return sum
    End Function
    Structure mahsanit
        Dim nom As String
        Dim nb_nom As Integer
    End Structure
    Function input_mahsanit(ByVal a As String, ByVal b As Integer)
        Dim debut As mahsanit
        debut.nom = a
        debut.nb_nom = b
        Return debut
    End Function
    Sub Printmahsanit(ByVal c As mahsanit)
        Console.WriteLine("{0} : {1} ", c.nom, c.nb_nom)
    End Sub
    Structure devis
        Dim patisserie As String
        Dim nb_pat As Integer
        Dim prix_pat As Integer
    End Structure
    'struct miyoun
    Function input(ByVal a As String, ByVal b As Integer, ByVal c As Integer) As devis
        Dim res As devis
        res.patisserie = a
        res.nb_pat = b
        res.prix_pat = c
        Return res
    End Function
    Sub Swap(ByRef arr() As devis, ByVal a As Integer, ByVal b As Integer)
        Dim temp As devis = arr(a)
        arr(a) = arr(b)
        arr(b) = temp
    End Sub
    Function FindMin(ByVal arr() As devis, ByVal start As Integer) As Integer
        Dim res As Integer = start
        For i As Integer = start To arr.Length() - 1
            If arr(i).prix_pat < arr(res).prix_pat Then res = i
        Next
        Return res
    End Function
    Sub SelectionSort(ByVal arr() As devis)
        For i = 0 To arr.Length() - 2
            Swap(arr, i, FindMin(arr, i))
        Next
    End Sub
    Sub Printdevis(ByVal c As devis)
        If c.prix_pat > 0 Then
            Console.WriteLine("{1} {0} : {2} shekel ", c.patisserie, c.nb_pat, c.prix_pat)
        End If
    End Sub
    Sub Main()
        'donnees client
        Console.WriteLine()
        Console.WriteLine(" ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~")
        Console.WriteLine(" boulangerie : Ganizlev ; since 2007 ")
        Console.WriteLine(" ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~")
        Console.WriteLine()
        Dim client(0) As donne_client
        client(0) = New donne_client
        client(0).set_datachange()
        Console.WriteLine("~~~~~~~~~~~~~~~~~~~~~~~~~~~~")
        Dim nom_gateaux(2) As String
        nom_gateaux(0) = "brioche" : nom_gateaux(1) = "flan" : nom_gateaux(2) = "fraisier"
        Dim comp As New ArrayList
        Dim ver As String
        Dim count As Integer
        Console.WriteLine()
        Console.WriteLine("Let's start the order ")
        Console.WriteLine()
        While True
            Console.WriteLine("what do you want ?")
            Console.WriteLine("brioche/flan/fraisier")
            Dim gtx As String = verification3(Console.ReadLine())
            comp.Add(gtx)
            If count < 2 Then
                Console.WriteLine("do you want an other patisserie")
                Console.WriteLine("yes/no")
                ver = verification(Console.ReadLine)
                Console.WriteLine()
                If ver = "no" Or ver = "NO" Or ver = "No" Then
                    count += 1
                    Exit While
                End If
            End If
            count += 1
            If count = 3 Then Exit While
        End While
        Console.WriteLine()
        Console.WriteLine("~~~~~~~~~~~~~~~~~~~~~~~~~~~~")
        Console.WriteLine()
        Dim debut(count - 1) As mahsanit
        Dim nb1, nb2, nb3 As Integer
        'hipous
        For i As Integer = 0 To count - 1
            If comp(i) = nom_gateaux(0) Then
                Console.WriteLine("how many brioche do you want ? ")
                nb1 = (Console.ReadLine)
                Console.WriteLine()
                debut(i) = input_mahsanit("brioche", nb1)
            ElseIf comp(i) = nom_gateaux(1) Then
                Console.WriteLine("how many flan do you want ? ")
                nb2 = (Console.ReadLine)
                Console.WriteLine()
                debut(i) = input_mahsanit("flan", nb2)
            ElseIf comp(i) = nom_gateaux(2) Then
                Console.WriteLine("how many fraisier do you want ? ")
                nb3 = (Console.ReadLine)
                Console.WriteLine()
                debut(i) = input_mahsanit("fraisier", nb3)
            End If
        Next
        Console.WriteLine()
        Console.WriteLine("OK, here the brief of the order")
        Console.WriteLine()
        'mahsanit
        For Each c As mahsanit In debut
            Printmahsanit(c)
        Next
        Console.WriteLine()
        Console.WriteLine("~~~~~~~~~~~~~~~~~~~~~~~~~~~~")
        Console.WriteLine()

        Dim brioche As New brioche(nb1)
        Dim flan As New flan(nb2)
        Dim fraisier As New fraisier(nb3)
        Console.WriteLine()
        Dim brioche_cost As Integer = price(
brioche.get_prix_oeufs_brioche,
brioche.get_prix_farine_brioche(brioche.get_farine_brioche),
brioche.get_prix_sucre_brioche(brioche.get_cout_horraire_brioche),
brioche.get_cout_horraire_brioche) * 1.2
        Dim flan_cost As Integer = price(
        flan.get_prix_oeufs_flan(flan.get_oeufs_flan),
        flan.get_prix_farine_flan(flan.get_farine_flan),
        flan.get_prix_sucre_flan(flan.get_sucre_flan),
        flan.get_cout_horraire_flan) * 2.8
        Dim fraisier_cost As Integer = price(
        fraisier.get_prix_oeufs_fraisier(fraisier.get_oeufs_fraisier),
        fraisier.get_prix_farine_fraisier(fraisier.get_farine_fraisier),
        fraisier.get_prix_sucre_fraisier(fraisier.get_sucre_fraisier),
        fraisier.get_cout_horraire_fraisier) * 2
        Dim total_cost As Integer = price(brioche_cost, flan_cost, fraisier_cost, 0)
        ' changement de nb
        Console.WriteLine()
        Console.WriteLine("Your command is ok?")
        Console.WriteLine("yes/no")
        Dim change As String = verification(Console.ReadLine)
        While change = "no" Or change = "No" Or change = "NO"
            Console.WriteLine()
            Console.WriteLine("what do you want to add or change")
            Console.WriteLine("brioche/flan/fraisier")
            Dim gateaux As String = verification3(Console.ReadLine())
            If gateaux = "brioche" Then
                Console.WriteLine("how many brioche do you want ? ")
                brioche.set_brioche(Console.ReadLine)
            ElseIf gateaux = "flan" Then
                Console.WriteLine("how many flan do you want ? ")
                flan.set_flan(Console.ReadLine)
            ElseIf gateaux = "fraisier" Then
                Console.WriteLine("how many fraisier do you want ? ")
                fraisier.set_fraisier(Console.ReadLine)
            End If
            brioche_cost = price(
brioche.get_prix_oeufs_brioche,
brioche.get_prix_farine_brioche(brioche.get_farine_brioche),
brioche.get_prix_sucre_brioche(brioche.get_sucre_brioche),
brioche.get_cout_horraire_brioche) * 1.2
            flan_cost = price(
flan.get_prix_oeufs_flan(flan.get_oeufs_flan),
flan.get_prix_farine_flan(flan.get_farine_flan),
flan.get_prix_sucre_flan(flan.get_sucre_flan),
flan.get_cout_horraire_flan) * 2.8
            fraisier_cost = price(
fraisier.get_prix_oeufs_fraisier(fraisier.get_oeufs_fraisier),
fraisier.get_prix_farine_fraisier(fraisier.get_farine_fraisier),
fraisier.get_prix_sucre_fraisier(fraisier.get_sucre_fraisier),
fraisier.get_cout_horraire_fraisier) * 2
            total_cost = price(brioche_cost, flan_cost, fraisier_cost, 0)
            Console.WriteLine()
            Console.WriteLine("Do you want to change an other patisserie ?")
            Console.WriteLine("yes/no")
            Dim choix As String = verification(Console.ReadLine)
            If choix = "NO" Or choix = "no" Or choix = "No" Then Exit While
        End While
        Console.WriteLine()
        Console.WriteLine("~~~~~~~~~~~~~~~~~~~~~~~~~~~~")
        Console.WriteLine()
        ' miyoun
        Console.WriteLine("this is your receipt ")
        Dim arr(2) As devis
        arr(0) = input("brioche", brioche.get_nb_brioche, brioche_cost)
        arr(1) = input("flan", flan.get_nb_flan, flan_cost)
        arr(2) = input("fraisier", fraisier.get_nb_fraisier, fraisier_cost)
        SelectionSort(arr)
        client(0).get_print()
        For Each c As devis In arr
            Printdevis(c)
        Next
        Console.WriteLine()
        Console.WriteLine("Total of the order: " & total_cost & " shekels")
        Console.WriteLine()
        Console.WriteLine("Thank you ! We would like to see you again ! ")
        Console.WriteLine("~~~~~~~~~~~~~~~~~~~~~~~~~~~~")
        Console.WriteLine()
        Console.WriteLine("For the pastry chef ")
        Console.WriteLine("Do you want to see what you will need tobuy ? ")
        Console.WriteLine("yes/no")
        Console.WriteLine()
        Dim a As String = verification(Console.ReadLine)
        Dim oeufs As Integer = brioche.get_oeufs_brioche() + flan.get_oeufs_flan() + flan.get_oeufs_flan()
        Dim farine As Integer = brioche.get_farine_brioche() + flan.get_farine_flan() + fraisier.get_farine_fraisier()
        Dim sucre As Integer = brioche.get_sucre_brioche() + flan.get_sucre_flan() + fraisier.get_sucre_fraisier()
        Dim oeufs_prix As Integer = price(brioche.get_prix_oeufs_brioche, brioche.get_prix_farine_brioche(brioche.get_farine_brioche),
brioche.get_prix_sucre_brioche(brioche.get_sucre_brioche),
brioche.get_cout_horraire_brioche)
        Dim farine_prix As Integer = price(flan.get_prix_oeufs_flan(flan.get_oeufs_flan), flan.get_prix_farine_flan(flan.get_farine_flan),
flan.get_prix_sucre_flan(flan.get_sucre_flan),
flan.get_cout_horraire_flan)
        Dim sucre_prix As Integer = price(
fraisier.get_prix_oeufs_fraisier(fraisier.get_oeufs_fraisier),
fraisier.get_prix_farine_fraisier(fraisier.get_farine_fraisier),
fraisier.get_prix_sucre_fraisier(fraisier.get_sucre_fraisier),
fraisier.get_cout_horraire_fraisier)
        If a = "yes" Or a = "Yes" Or a = "YES" Then
            Console.WriteLine("egs : " & oeufs)
            Console.WriteLine("flour : " & farine & " g")
            Console.WriteLine("sugar : " & sucre & " g")
            Console.WriteLine("here is the total price of your next purchases around : " & oeufs_prix + farine_prix + sucre_prix & " shekel")
            Console.WriteLine(" good luck with your shopping ")
        Else
            Console.WriteLine("Thank you ! See you soon ")
        End If

        Console.ReadKey()
    End Sub
End Module
