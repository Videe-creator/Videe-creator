![IMG-20241023-WA0009](https://github.com/user-attachments/assets/664b66cc-13ff-4df1-9629-8620a6773a53)
'use client'

import { useState } from 'react'
import { Card, CardContent, CardHeader, CardTitle } from "@/components/ui/card"
import { Tabs, TabsContent, TabsList, TabsTrigger } from "@/components/ui/tabs"
import { Button } from "@/components/ui/button"
import { Input } from "@/components/ui/input"
import { Label } from "@/components/ui/label"
import { Table, TableBody, TableCell, TableHead, TableHeader, TableRow } from "@/components/ui/table"
import { Glasses, Box, DollarSign, Stethoscope, Scissors, ChevronLeft, ChevronRight } from 'lucide-react'
import { LineChart, Line, XAxis, YAxis, CartesianGrid, Tooltip, ResponsiveContainer } from 'recharts'

export default function Dashboard() {
  const [activeTab, setActiveTab] = useState("inventory")
  const [isLoading, setIsLoading] = useState(false)
  const [error, setError] = useState<string | null>(null)
  const [currentPage, setCurrentPage] = useState(1)
  const itemsPerPage = 5

  const inventoryData = [
    { id: 1, name: "Ray-Ban Aviator", type: "Frame", quantity: 50, price: 129.99 },
    { id: 2, name: "Oakley Holbrook", type: "Frame", quantity: 30, price: 99.99 },
    { id: 3, name: "Essilor Crizal", type: "Lens", quantity: 100, price: 79.99 },
    { id: 4, name: "Hardcase Black", type: "Case", quantity: 200, price: 9.99 },
    { id: 5, name: "3-Tier Frame Stand", type: "Equipment", quantity: 10, price: 49.99 },
    { id: 6, name: "Cleaning Cloth", type: "Accessory", quantity: 500, price: 2.99 },
    { id: 7, name: "Contact Lens Solution", type: "Accessory", quantity: 75, price: 12.99 },
  ]

  const equipmentData = [
    { id: 1, name: "Topcon KR-800", type: "Auto Refractor", lastMaintenance: "2023-05-15" },
    { id: 2, name: "Nidek LE-700", type: "Lens Edger", lastMaintenance: "2023-06-01" },
    { id: 3, name: "Zeiss Visucam", type: "Fundus Camera", lastMaintenance: "2023-04-22" },
  ]

  const salesData = [
    { name: 'Jan', sales: 
