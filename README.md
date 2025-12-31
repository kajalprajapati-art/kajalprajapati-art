import { Card, CardContent } from "@/components/ui/card";
import { Github, BarChart3, Users, Phone, Pizza } from "lucide-react";
import { motion } from "framer-motion";

export default function Portfolio() {
  const projects = [
    {
      title: "Customer Retention Analysis",
      desc: "Interactive Power BI dashboard analyzing churn drivers and customer behavior.",
      icon: <BarChart3 size={28} />,
      link: "https://github.com/kajalprajapati-art/Customer-Rentention",
      tags: ["Power BI", "DAX", "Churn Analysis", "KPIs"],
    },
    {
      title: "Diversity & Inclusion Dashboard",
      desc: "HR analytics dashboard measuring diversity, promotions, and workforce equity.",
      icon: <Users size={28} />,
      link: "https://github.com/kajalprajapati-art/Diversity-and-inclusion-Dashboard",
      tags: ["HR Analytics", "Power BI", "People Analytics"],
    },
    {
      title: "Call Centre Analytics",
      desc: "Performance tracking of agents, calls, and customer satisfaction metrics.",
      icon: <Phone size={28} />,
      link: "https://github.com/kajalprajapati-art/Call-Centre-Data-Analysis",
      tags: ["Operations", "CX Analytics", "Dashboards"],
    },
    {
      title: "Pizza Sales Analysis",
      desc: "Sales insights dashboard identifying revenue trends and product performance.",
      icon: <Pizza size={28} />,
      link: "https://github.com/kajalprajapati-art/Pizza-Sales-Analysis",
      tags: ["Sales Analytics", "Retail BI", "Revenue"],
    },
  ];

  return (
    <div className="min-h-screen bg-gradient-to-br from-gray-950 to-gray-900 text-white p-10">
      <motion.h1
        initial={{ opacity: 0, y: -20 }}
        animate={{ opacity: 1, y: 0 }}
        className="text-4xl font-bold text-center mb-4"
      >
        Kajal Prajapati
      </motion.h1>
      <p className="text-center text-gray-400 mb-12">
        Data Analyst • Power BI Developer • Business Intelligence
      </p>

      <div className="grid grid-cols-1 md:grid-cols-2 gap-8 max-w-6xl mx-auto">
        {projects.map((p, i) => (
          <motion.div
            key={i}
            initial={{ opacity: 0, y: 30 }}
            whileInView={{ opacity: 1, y: 0 }}
            transition={{ delay: i * 0.1 }}
          >
            <Card className="bg-gray-900 border-gray-800 hover:border-indigo-500 transition">
              <CardContent className="p-6">
                <div className="flex items-center gap-4 mb-4 text-indigo-400">
                  {p.icon}
                  <h2 className="text-xl font-semibold">{p.title}</h2>
                </div>
                <p className="text-gray-400 mb-4">{p.desc}</p>
                <div className="flex flex-wrap gap-2 mb-4">
                  {p.tags.map((t, idx) => (
                    <span
                      key={idx}
                      className="text-xs bg-indigo-600/20 text-indigo-300 px-3 py-1 rounded-full"
                    >
                      {t}
                    </span>
                  ))}
                </div>
                <a
                  href={p.link}
                  target="_blank"
                  className="inline-flex items-center gap-2 text-sm text-indigo-400 hover:underline"
                >
                  <Github size={16} /> View Repository
                </a>
              </CardContent>
            </Card>
          </motion.div>
        ))}
      </div>
    </div>
  );
}
