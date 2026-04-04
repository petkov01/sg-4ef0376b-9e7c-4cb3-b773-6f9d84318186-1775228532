// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ
// FILE: src/app/routes.tsx
// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ

import { createBrowserRouter, Outlet, useLocation, Link } from "react-router";
import { LandingPage } from "./pages/LandingPage";
import { LoginPage } from "./pages/LoginPage";
import { RegisterPage } from "./pages/RegisterPage";
import { NotFoundPage } from "./pages/NotFoundPage";
import { CodeExportPage } from "./pages/CodeExportPage";
import { PricingPage } from "./pages/PricingPage";
import { ClientShell } from "./components/ClientShell";
import { ProShell } from "./components/ProShell";
import { ClientDashboard } from "./pages/ClientDashboard";
import { ProjectWizardPage } from "./pages/client/ProjectWizardPage";
import { ProjectsPage } from "./pages/client/ProjectsPage";
import { ChatPage } from "./pages/client/ChatPage";
import { MarketplacePage } from "./pages/client/MarketplacePage";
import { DocumentsPage } from "./pages/client/DocumentsPage";
import { CommunityPage } from "./pages/client/CommunityPage";
import { SettingsPage } from "./pages/client/SettingsPage";
// PRO pages
import { ProDashboard } from "./pages/pro/ProDashboard";
import { ProAIPage } from "./pages/pro/ProAIPage";
import { ProKSSPage } from "./pages/pro/ProKSSPage";
import { ProProjectsPage } from "./pages/pro/ProProjectsPage";
import { ProContractsPage } from "./pages/pro/ProContractsPage";
import { ProInvoicesPage } from "./pages/pro/ProInvoicesPage";
import { ProWorkersPage } from "./pages/pro/ProWorkersPage";
import { ProDocumentsProPage } from "./pages/pro/ProDocumentsProPage";
import { ProAssetsPage } from "./pages/pro/ProAssetsPage";
import { ProInquiriesPage } from "./pages/pro/ProInquiriesPage";
import { ProMessagesPage } from "./pages/pro/ProMessagesPage";
import { ProTeamPage } from "./pages/pro/ProTeamPage";
import { ProAnalyticsPage } from "./pages/pro/ProAnalyticsPage";
import { ProGooglePage } from "./pages/pro/ProGooglePage";
import { ProSettingsPage } from "./pages/pro/ProSettingsPage";
// PRO Tools
import { ProAIOverviewPage } from "./pages/pro/tools/ProAIOverviewPage";
import { Pro3DVisualizerPage } from "./pages/pro/tools/Pro3DVisualizerPage";
import { ProSketchPage } from "./pages/pro/tools/ProSketchPage";
import { ProAIAssistantToolPage } from "./pages/pro/tools/ProAIAssistantToolPage";
import { ProAIStatsPage } from "./pages/pro/tools/ProAIStatsPage";
import { FileCode2 } from "lucide-react";

// в”Ђв”Ђ Root wrapper в”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђ
function Root() {
  const location = useLocation();
  const path = location.pathname;
  const isCodePage    = path === "/code-export";
  const isPricingPage = path === "/pricing";
  const isClientArea  = path.startsWith("/client") || path.startsWith("/community");
  const isProArea     = path.startsWith("/pro");

  return (
    <>
      <Outlet />
      <div style={{ position:"fixed", bottom:20, right:20, zIndex:9999, display:"flex", flexDirection:"column", gap:8, alignItems:"flex-end" }}>
        {!isClientArea && (
          <Link to="/client" style={{ display:"flex", alignItems:"center", gap:8, padding:"9px 16px", borderRadius:14, background:"linear-gradient(135deg,#6366f1,#2563EB)", color:"#fff", textDecoration:"none", boxShadow:"0 6px 20px rgba(99,102,241,.35)", fontSize:13, fontWeight:600 }}>
            рџЏ  РљР»РёРµРЅС‚
          </Link>
        )}
        {!isProArea && (
          <Link to="/pro" style={{ display:"flex", alignItems:"center", gap:8, padding:"9px 16px", borderRadius:14, background:"linear-gradient(135deg,#f59e0b,#d97706)", color:"#fff", textDecoration:"none", boxShadow:"0 6px 20px rgba(245,158,11,.35)", fontSize:13, fontWeight:600 }}>
            рџ‘‘ PRO Р¤РёСЂРјР°
          </Link>
        )}
        {!isPricingPage && (
          <Link to="/pricing" style={{ display:"flex", alignItems:"center", gap:8, padding:"9px 16px", borderRadius:14, background:"linear-gradient(135deg,#0D9488,#2563EB)", color:"#fff", textDecoration:"none", boxShadow:"0 6px 20px rgba(13,148,136,.30)", fontSize:13, fontWeight:600 }}>
            рџ’Ћ Р¦РµРЅРё
          </Link>
        )}
        {!isCodePage && (
          <Link to="/code-export" style={{ display:"flex", alignItems:"center", gap:8, padding:"9px 16px", borderRadius:14, background:"linear-gradient(135deg,#2563EB,#0D9488)", color:"#fff", textDecoration:"none", boxShadow:"0 8px 24px rgba(37,99,235,.30)", fontSize:13, fontWeight:600 }}>
            <FileCode2 size={16} />
            РљРѕРґ
          </Link>
        )}
      </div>
    </>
  );
}

// в”Ђв”Ђв”Ђ Router в”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђ
export const router = createBrowserRouter([
  {
    path: "/",
    Component: Root,
    children: [
      // в”Ђв”Ђ Public в”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђ
      { index: true,         element: <LandingPage /> },
      { path: "login",       element: <LoginPage /> },
      { path: "register",    element: <RegisterPage /> },
      { path: "pricing",     element: <PricingPage /> },
      { path: "code-export", element: <CodeExportPage /> },

      // в”Ђв”Ђ Community в”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђ
      { path: "community", element: <ClientShell><CommunityPage /></ClientShell> },

      // в”Ђв”Ђ Client Portal в”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђ
      {
        path: "client",
        element: <ClientShell />,
        children: [
          { index: true,            element: <ClientDashboard /> },
          { path: "project-wizard", element: <ProjectWizardPage /> },
          { path: "projects",       element: <ProjectsPage /> },
          { path: "chat",           element: <ChatPage /> },
          { path: "marketplace",    element: <MarketplacePage /> },
          { path: "documents",      element: <DocumentsPage /> },
          { path: "settings",       element: <SettingsPage /> },
        ],
      },

      // в”Ђв”Ђ PRO Portal в”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђ
      {
        path: "pro",
        element: <ProShell />,
        children: [
          { index: true,              element: <ProDashboard /> },
          { path: "ai",               element: <ProAIPage /> },
          { path: "kss",              element: <ProKSSPage /> },
          { path: "projects",         element: <ProProjectsPage /> },
          { path: "contracts",        element: <ProContractsPage /> },
          { path: "invoices",         element: <ProInvoicesPage /> },
          { path: "workers",          element: <ProWorkersPage /> },
          { path: "documents-pro",    element: <ProDocumentsProPage /> },
          { path: "assets",           element: <ProAssetsPage /> },
          // РРЅСЃС‚СЂСѓРјРµРЅС‚Рё (Tools)
          { path: "tools/ai-overview",element: <ProAIOverviewPage /> },
          { path: "tools/3d",         element: <Pro3DVisualizerPage /> },
          { path: "tools/sketch",     element: <ProSketchPage /> },
          { path: "tools/assistant",  element: <ProAIAssistantToolPage /> },
          { path: "tools/ai-stats",   element: <ProAIStatsPage /> },
          // Other
          { path: "inquiries",        element: <ProInquiriesPage /> },
          { path: "messages",         element: <ProMessagesPage /> },
          { path: "team",             element: <ProTeamPage /> },
          { path: "analytics",        element: <ProAnalyticsPage /> },
          { path: "google",           element: <ProGooglePage /> },
          { path: "settings",         element: <ProSettingsPage /> },
        ],
      },

      // в”Ђв”Ђ Catch-all в”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђ
      { path: "*", element: <NotFoundPage /> },
    ],
  },
]);



// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ
// FILE: src/app/components/ProShell.tsx
// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ

import { TemaDomLogo } from "./TemaDomLogo";
import { ZenithWidget } from "./ZenithWidget";
import { useState, useMemo } from "react";
import { Link, NavLink, Outlet, useNavigate, useLocation } from "react-router";
import {
  LayoutDashboard, Bot, Calculator, FolderKanban, FileText,
  Users, BarChart3, Settings, LogOut, Menu, X, Search,
  ChevronRight, Bell, Zap, Crown, Receipt, Chrome,
  HardHat, FolderArchive, Package, Wrench, Sparkles,
  Box, Pencil, MessageSquare, ChevronDown, Download, AlertTriangle,
} from "lucide-react";

// в”Ђв”Ђв”Ђ Nav structure в”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђ
interface NavLeaf {
  kind: "leaf";
  label: string;
  icon: React.FC<{ className?: string }>;
  to: string;
  end?: boolean;
  badge?: string;
}
interface NavGroup {
  kind: "group";
  label: string;
  icon: React.FC<{ className?: string }>;
  children: NavLeaf[];
}
type NavEntry = NavLeaf | NavGroup;

const NAV: NavEntry[] = [
  { kind:"leaf",  label:"РќР°С‡Р°Р»Рѕ",      icon:LayoutDashboard, to:"/pro",             end:true },
  { kind:"leaf",  label:"ZENITH AI",   icon:Bot,             to:"/pro/ai",          badge:"AI" },
  { kind:"leaf",  label:"РљРЎРЎ",         icon:Calculator,      to:"/pro/kss" },
  { kind:"leaf",  label:"РџСЂРѕРµРєС‚Рё",     icon:FolderKanban,    to:"/pro/projects" },
  { kind:"leaf",  label:"Р”РѕРіРѕРІРѕСЂРё",    icon:FileText,        to:"/pro/contracts" },
  { kind:"leaf",  label:"Р¤Р°РєС‚СѓСЂРё",     icon:Receipt,         to:"/pro/invoices" },
  { kind:"leaf",  label:"Р Р°Р±РѕС‚РЅРёС†Рё",   icon:HardHat,         to:"/pro/workers" },
  { kind:"leaf",  label:"Р”РѕРєСѓРјРµРЅС‚Рё",   icon:FolderArchive,   to:"/pro/documents-pro" },
  { kind:"leaf",  label:"РђРєС‚РёРІРё",      icon:Package,         to:"/pro/assets" },
  {
    kind:"group", label:"РРЅСЃС‚СЂСѓРјРµРЅС‚Рё", icon:Sparkles,
    children:[
      { kind:"leaf", label:"AI РћРіР»РµРґ",       icon:Sparkles,      to:"/pro/tools/ai-overview" },
      { kind:"leaf", label:"3D Р’РёР·СѓР°Р»РёР·Р°С‚РѕСЂ",icon:Box,           to:"/pro/tools/3d" },
      { kind:"leaf", label:"IA Sketch",      icon:Pencil,        to:"/pro/tools/sketch" },
      { kind:"leaf", label:"AI РђСЃРёСЃС‚РµРЅС‚",    icon:Bot,           to:"/pro/tools/assistant" },
      { kind:"leaf", label:"AI РЎС‚Р°С‚РёСЃС‚РёРєР°",  icon:BarChart3,     to:"/pro/tools/ai-stats" },
    ],
  },
  { kind:"leaf", label:"Р—Р°РїРёС‚РІР°РЅРёСЏ",  icon:AlertTriangle,   to:"/pro/inquiries" },
  { kind:"leaf", label:"РЎСЉРѕР±С‰РµРЅРёСЏ",  icon:MessageSquare,    to:"/pro/messages" },
  { kind:"leaf", label:"Р•РєРёРї",        icon:Users,           to:"/pro/team" },
  { kind:"leaf", label:"РђРЅР°Р»РёР·Рё",     icon:BarChart3,       to:"/pro/analytics" },
  { kind:"leaf", label:"Google",      icon:Chrome,          to:"/pro/google",    badge:"G" },
  { kind:"leaf", label:"РќР°СЃС‚СЂРѕР№РєРё",   icon:Settings,        to:"/pro/settings" },
];

const FIRM = { name:"РЎРљ РЎС‚СЂРѕР№ Р•РћРћР”", plan:"РџСЂРµРјРёСѓРј AI", initials:"РЎРЎ" };

// в”Ђв”Ђв”Ђ Leaf nav item в”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђ
function LeafItem({ item, onClose, indent }: { item: NavLeaf; onClose?: () => void; indent?: boolean }) {
  const Icon = item.icon;
  return (
    <NavLink to={item.to} end={item.end} onClick={onClose}
      className={({ isActive }) =>
        `flex items-center gap-3 px-3 py-2.5 rounded-xl mb-0.5 transition-all group ${indent ? "ml-3 pl-2.5" : ""} ${
          isActive ? "bg-blue-50 text-blue-700" : "text-gray-600 hover:bg-gray-100 hover:text-gray-900"
        }`
      }
    >
      {({ isActive }) => (
        <>
          <Icon className={`size-4 flex-shrink-0 transition-transform group-hover:scale-110 ${isActive ? "text-blue-600" : "text-gray-400 group-hover:text-gray-700"}`} />
          <span className={`text-sm flex-1 ${isActive ? "font-medium" : ""}`}>{item.label}</span>
          {item.badge && (
            <span className={`px-1.5 py-0.5 rounded-full text-[9px] ${item.badge==="AI" ? "bg-gradient-to-r from-blue-600 to-teal-500 text-white" : "bg-blue-100 text-blue-600"}`}>
              {item.badge}
            </span>
          )}
          {isActive && !item.badge && <ChevronRight className="size-3.5 text-blue-400 flex-shrink-0" />}
        </>
      )}
    </NavLink>
  );
}

// в”Ђв”Ђв”Ђ Group nav item в”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђ
function GroupItem({ item, onClose }: { item: NavGroup; onClose?: () => void }) {
  const location = useLocation();
  const anyActive = item.children.some(c => location.pathname.startsWith(c.to));
  const [open, setOpen] = useState(anyActive);
  const Icon = item.icon;

  return (
    <div>
      <button onClick={() => setOpen(v => !v)}
        className={`w-full flex items-center gap-3 px-3 py-2.5 rounded-xl mb-0.5 transition-all group ${anyActive ? "bg-blue-50 text-blue-700" : "text-gray-600 hover:bg-gray-100 hover:text-gray-900"}`}>
        <Icon className={`size-4 flex-shrink-0 ${anyActive ? "text-blue-600" : "text-gray-400 group-hover:text-gray-700"}`} />
        <span className={`text-sm flex-1 text-left ${anyActive ? "font-medium" : ""}`}>{item.label}</span>
        <ChevronDown className={`size-3.5 flex-shrink-0 transition-transform ${open ? "rotate-180" : ""} ${anyActive ? "text-blue-400" : "text-gray-400"}`} />
      </button>
      {open && (
        <div className="ml-2 mb-1 border-l-2 border-blue-100 pl-2 space-y-0.5">
          {item.children.map(child => (
            <LeafItem key={child.to} item={child} onClose={onClose} />
          ))}
        </div>
      )}
    </div>
  );
}

// в”Ђв”Ђв”Ђ Sidebar в”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђ
function SidebarContent({ onClose }: { onClose?: () => void }) {
  const [q, setQ] = useState("");
  const navigate = useNavigate();

  const allLeaves: NavLeaf[] = NAV.flatMap(e => e.kind==="leaf" ? [e] : e.children);
  const filtered = useMemo(
    () => allLeaves.filter(l => l.label.toLowerCase().includes(q.toLowerCase())),
    [q]
  );

  return (
    <div className="flex flex-col h-full">
      {/* Logo */}
      <div className="flex items-center justify-between px-5 py-5 border-b border-gray-100">
        <Link to="/" onClick={onClose}><TemaDomLogo size="sm" instanceId="pro-sidebar" /></Link>
        {onClose && (
          <button onClick={onClose} className="size-8 flex items-center justify-center rounded-lg text-gray-400 hover:bg-gray-100 lg:hidden">
            <X className="size-5" />
          </button>
        )}
      </div>

      {/* PRO badge */}
      <div className="px-4 pt-4 pb-2">
        <div className="flex items-center gap-2 px-3 py-2 rounded-xl bg-gradient-to-r from-amber-50 to-orange-50 border border-amber-200">
          <Crown className="size-3.5 text-amber-500" />
          <span className="text-xs text-amber-700">РџР Рћ РџР›РђРўР¤РћР РњРђ</span>
          <span className="ml-auto px-1.5 py-0.5 rounded-full bg-amber-500 text-white text-[10px]">PRO</span>
        </div>
      </div>

      {/* Search */}
      <div className="px-4 pb-2">
        <div className="relative">
          <Search className="absolute left-3 top-1/2 -translate-y-1/2 size-3.5 text-gray-400 pointer-events-none" />
          <input type="text" placeholder="РўСЉСЂСЃРё РІ РјРµРЅСЋС‚Рѕ..." value={q} onChange={e=>setQ(e.target.value)}
            className="w-full pl-8 pr-3 py-2 text-xs bg-gray-50 border border-gray-200 rounded-xl text-gray-700 placeholder-gray-400 focus:outline-none focus:ring-2 focus:ring-blue-500/20 focus:border-blue-400 transition-all" />
        </div>
      </div>

      {/* Nav */}
      <nav className="flex-1 px-3 py-1 overflow-y-auto space-y-0.5">
        {q
          ? filtered.length === 0
            ? <p className="text-xs text-gray-400 text-center py-6">РќСЏРјР° СЂРµР·СѓР»С‚Р°С‚Рё</p>
            : filtered.map(l => <LeafItem key={l.to} item={l} onClose={onClose} />)
          : NAV.map((entry, i) => (
              <div key={i}>
                {/* Separators */}
                {(entry.kind==="leaf" && (entry.to==="/pro/inquiries" || entry.to==="/pro/team")) && (
                  <div className="my-2 mx-1 border-t border-gray-100" />
                )}
                {entry.kind==="leaf"
                  ? <LeafItem item={entry} onClose={onClose} />
                  : <GroupItem item={entry} onClose={onClose} />
                }
              </div>
            ))
        }
      </nav>

      {/* Bottom actions */}
      <div className="px-4 py-3 border-t border-gray-50 space-y-1">
        <button className="w-full flex items-center gap-2.5 px-3 py-2 rounded-xl text-gray-500 hover:bg-gray-100 transition-all text-sm">
          <Download className="size-4 flex-shrink-0" />
          РЎРІР°Р»Рё РїСЂРёР»РѕР¶РµРЅРёРµС‚Рѕ
        </button>
        <button className="w-full flex items-center gap-2.5 px-3 py-2 rounded-xl text-amber-600 hover:bg-amber-50 transition-all text-sm">
          <AlertTriangle className="size-4 flex-shrink-0" />
          Р”РѕРєР»Р°РґРІР°Р№ РїСЂРѕР±Р»РµРј
        </button>
      </div>

      {/* Firm + logout */}
      <div className="px-4 py-4 border-t border-gray-100">
        <div className="flex items-center gap-3 mb-3 px-1">
          <div className="size-8 rounded-full bg-gradient-to-br from-violet-500 to-blue-600 flex items-center justify-center text-white text-xs flex-shrink-0">
            {FIRM.initials}
          </div>
          <div className="min-w-0">
            <p className="text-sm text-gray-800 truncate">{FIRM.name}</p>
            <p className="text-xs text-amber-600">{FIRM.plan}</p>
          </div>
        </div>
        <button onClick={() => navigate("/login")}
          className="w-full flex items-center gap-2.5 px-3 py-2.5 rounded-xl text-red-500 hover:bg-red-50 hover:text-red-600 transition-all group">
          <LogOut className="size-4 flex-shrink-0 group-hover:-translate-x-0.5 transition-transform" />
          <span className="text-sm">РР·С…РѕРґ</span>
        </button>
      </div>
    </div>
  );
}

// в”Ђв”Ђв”Ђ Main Shell в”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђ
export function ProShell({ children }: { children?: React.ReactNode }) {
  const [mobileOpen, setMobileOpen] = useState(false);
  const navigate = useNavigate();

  return (
    <div className="flex h-screen bg-gray-50 overflow-hidden">
      {/* Desktop sidebar */}
      <aside className="hidden lg:flex flex-col w-64 bg-white border-r border-gray-100 flex-shrink-0">
        <SidebarContent />
      </aside>

      {/* Mobile overlay */}
      {mobileOpen && (
        <div className="lg:hidden fixed inset-0 z-50 flex">
          <div className="absolute inset-0 bg-black/40 backdrop-blur-sm" onClick={() => setMobileOpen(false)} />
          <aside className="relative z-10 w-72 bg-white h-full shadow-2xl flex flex-col">
            <SidebarContent onClose={() => setMobileOpen(false)} />
          </aside>
        </div>
      )}

      {/* Main */}
      <div className="flex-1 flex flex-col min-w-0 overflow-hidden">
        {/* Header */}
        <header className="h-16 bg-white border-b border-gray-100 flex items-center px-4 lg:px-6 gap-3 flex-shrink-0">
          <button onClick={() => setMobileOpen(true)} className="lg:hidden size-9 flex items-center justify-center rounded-xl text-gray-500 hover:bg-gray-100 transition-colors">
            <Menu className="size-5" />
          </button>
          <Link to="/" className="lg:hidden">
            <TemaDomLogo size="sm" instanceId="pro-header-mob" />
          </Link>
          <div className="hidden sm:flex items-center gap-2 px-3 py-1.5 rounded-full bg-gradient-to-r from-amber-50 to-orange-50 border border-amber-200">
            <Crown className="size-3 text-amber-500" />
            <span className="text-xs text-amber-700 tracking-wide">РџР Рћ Р¤РР РњР•РќРђ РЎР Р•Р”Рђ</span>
          </div>
          <div className="flex-1" />
          <button className="relative size-9 flex items-center justify-center rounded-xl text-gray-500 hover:bg-gray-100 transition-colors">
            <Bell className="size-4" />
            <span className="absolute top-1.5 right-1.5 size-2 rounded-full bg-red-500" />
          </button>
          <button onClick={() => navigate("/pro/ai")}
            className="hidden sm:flex items-center gap-1.5 px-3 py-2 rounded-xl bg-gradient-to-r from-blue-600 to-teal-600 hover:from-blue-700 hover:to-teal-700 text-white text-sm transition-all shadow-md shadow-blue-200 active:scale-95">
            <Zap className="size-3.5" />
            ZENITH AI
          </button>
          <button onClick={() => navigate("/pro/settings")}
            className="size-9 rounded-full bg-gradient-to-br from-violet-500 to-blue-600 flex items-center justify-center text-white text-xs flex-shrink-0 hover:scale-105 transition-transform shadow-sm">
            {FIRM.initials}
          </button>
        </header>

        <main className="flex-1 overflow-y-auto">
          {children ?? <Outlet />}
        </main>
      </div>

      {/* в”Ђв”Ђ ZENITH AI вЂ” РїРѕСЃС‚РѕСЏРЅРµРЅ РІРёРґР¶РµС‚ РЅР° РІСЃСЏРєР° СЃС‚СЂР°РЅРёС†Р° в”Ђв”Ђ */}
      <ZenithWidget />
    </div>
  );
}


// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ
// FILE: src/app/components/ZenithWidget.tsx
// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ

import { useState, useRef, useEffect, useCallback } from "react";
import {
  Mic, MicOff, Send, X, Minimize2, Maximize2,
  Sparkles, Zap, Bot, Copy, ThumbsUp,
  ChevronDown, RotateCcw, Paperclip,
} from "lucide-react";

// в”Ђв”Ђв”Ђ Types в”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђ
interface Msg {
  id: string;
  role: "user" | "ai";
  text: string;
  time: string;
}

// в”Ђв”Ђв”Ђ Quick prompts в”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђ
const QUICK = [
  "РљР°РєРІРё СЃР° Р°РєС‚РёРІРЅРёС‚Рµ РјРё РїСЂРѕРµРєС‚Рё?",
  "РђРЅР°Р»РёР·РёСЂР°Р№ С„РёРЅР°РЅСЃРёС‚Рµ РјРё",
  "Р“РµРЅРµСЂРёСЂР°Р№ РґРѕРіРѕРІРѕСЂ",
  "РРјР°Рј Р»Рё РїСЂРѕСЃСЂРѕС‡РµРЅРё С„Р°РєС‚СѓСЂРё?",
];

// в”Ђв”Ђв”Ђ Mock AI responses в”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђ
const AI_RESP = [
  "Р Р°Р·Р±СЂР°С…! РђРЅР°Р»РёР·РёСЂР°Рј РґР°РЅРЅРёС‚Рµ РЅР° **РЎРљ РЎС‚СЂРѕР№ Р•РћРћР”** РІ СЂРµР°Р»РЅРѕ РІСЂРµРјРµ...\n\nР’РёР¶РґР°Рј **3 Р°РєС‚РёРІРЅРё РїСЂРѕРµРєС‚Р°** СЃ РѕР±С‰Р° СЃС‚РѕР№РЅРѕСЃС‚ ~220 000 Р»РІ. РџСЂРѕРµРєС‚ Р“РµСЂРјР°РЅ Рµ СЃ 8% РЅР°РїСЂРµРґ СЃРїСЂСЏРјРѕ РіСЂР°С„РёРєР° вЂ” РѕС‚Р»РёС‡РµРЅ СЂРµР·СѓР»С‚Р°С‚! РџСЂРµРїРѕСЂСЉС‡РІР°Рј РґР° С„РѕРєСѓСЃРёСЂР°С‚Рµ РІРЅРёРјР°РЅРёРµС‚Рѕ РІСЉСЂС…Сѓ РїСЂРѕСЃСЂРѕС‡РµРЅР°С‚Р° С„Р°РєС‚СѓСЂР° РѕС‚ Tech Soft OOD (12 450 Р»РІ).",
  "Р¤РёРЅР°РЅСЃРѕРІРёСЏС‚ Р°РЅР°Р»РёР· РїРѕРєР°Р·РІР° **СЃС‚Р°Р±РёР»РµРЅ СЂСЉСЃС‚ РѕС‚ 11%** СЃРїСЂСЏРјРѕ РјРёРЅР°Р»РёСЏ РјРµСЃРµС†. РћСЃРЅРѕРІРµРЅ СЂРёСЃРє: 36 900 Р»РІ РїСЂРѕСЃСЂРѕС‡РµРЅРё РІР·РµРјР°РЅРёСЏ РѕС‚ 2 РєР»РёРµРЅС‚Р°. РџСЂРµРїРѕСЂСЉС‡РІР°Рј Р°РІС‚РѕРјР°С‚РёС‡РЅРѕ РЅР°РїРѕРјРЅСЏРЅРµ + 2% Р»РёС…РІР° РїСЂРё Р·Р°Р±Р°РІСЏРЅРµ РЅР°Рґ 30 РґРЅРё.",
  "Р“РµРЅРµСЂРёСЂР°Рј СЃС‚Р°РЅРґР°СЂС‚РµРЅ РґРѕРіРѕРІРѕСЂ Р·Р° СЃС‚СЂРѕРёС‚РµР»СЃС‚РІРѕ РїРѕ **Р—РЈРў** СЃ РІР°С€РёС‚Рµ РґР°РЅРЅРё. Р’РєР»СЋС‡РІР°: РіР°СЂР°РЅС†РёРѕРЅРЅРё СЃСЂРѕРєРѕРІРµ, РЅРµСѓСЃС‚РѕР№РєРё, Р°РєС‚ 15/16. Р“РѕС‚РѕРІ Р·Р° РїСЂРµРіР»РµРґ РІ СЃРµРєС†РёСЏС‚Р° Р”РѕРіРѕРІРѕСЂРё.",
  "РќР°РјРµСЂРёС… **2 РїСЂРѕСЃСЂРѕС‡РµРЅРё С„Р°РєС‚СѓСЂРё**: Р¤Рљ-2026-025 (Tech Soft, 14 940 Р»РІ, 5 РґРЅРё РїСЂРѕСЃСЂРѕС‡РёРµ) Рё Р¤Рљ-2026-023 (Р•РЎ РР·С‚РѕРє, 4 350 Р»РІ, 6 РґРЅРё). РР·РїСЂР°С‰Р°Рј РЅР°РїРѕРјРЅСЏРЅРµ Рё РїРѕ РґРІРµС‚Рµ?",
];

let respIdx = 0;
const getResp = () => AI_RESP[respIdx++ % AI_RESP.length];

// в”Ђв”Ђв”Ђ Main Widget в”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђ
export function ZenithWidget() {
  const [open, setOpen]         = useState(false);
  const [expanded, setExpanded] = useState(false);
  const [msgs, setMsgs]         = useState<Msg[]>([]);
  const [input, setInput]       = useState("");
  const [loading, setLoading]   = useState(false);
  const [listening, setListening] = useState(false);
  const [transcript, setTranscript] = useState("");
  const [pulseRing, setPulseRing] = useState(false);
  const endRef  = useRef<HTMLDivElement>(null);
  const recognitionRef = useRef<SpeechRecognition | null>(null);

  // Pulse ring every 8s to draw attention when closed
  useEffect(() => {
    if (open) return;
    const timer = setInterval(() => {
      setPulseRing(true);
      setTimeout(() => setPulseRing(false), 1200);
    }, 8000);
    return () => clearInterval(timer);
  }, [open]);

  useEffect(() => {
    endRef.current?.scrollIntoView({ behavior: "smooth" });
  }, [msgs, loading]);

  // в”Ђв”Ђ Voice в”Ђв”Ђ
  const startListening = useCallback(() => {
    const SR = (window as any).SpeechRecognition || (window as any).webkitSpeechRecognition;
    if (!SR) { alert("Р‘СЂР°СѓР·СЉСЂСЉС‚ РІРё РЅРµ РїРѕРґРґСЉСЂР¶Р° РіР»Р°СЃРѕРІРѕ РІСЉРІРµР¶РґР°РЅРµ."); return; }
    const rec = new SR();
    rec.lang = "bg-BG";
    rec.continuous = false;
    rec.interimResults = true;
    rec.onstart = () => setListening(true);
    rec.onresult = (e: SpeechRecognitionEvent) => {
      const t = Array.from(e.results).map(r => r[0].transcript).join("");
      setTranscript(t);
      setInput(t);
    };
    rec.onend = () => {
      setListening(false);
      setTranscript("");
    };
    rec.onerror = () => setListening(false);
    recognitionRef.current = rec;
    rec.start();
  }, []);

  const stopListening = useCallback(() => {
    recognitionRef.current?.stop();
    setListening(false);
  }, []);

  // в”Ђв”Ђ Send в”Ђв”Ђ
  const send = (text?: string) => {
    const t = (text ?? input).trim();
    if (!t || loading) return;
    const userMsg: Msg = { id: Date.now().toString(), role:"user", text:t, time: now() };
    setMsgs(prev => [...prev, userMsg]);
    setInput(""); setTranscript("");
    setLoading(true);
    const delay = 900 + Math.random() * 600;
    setTimeout(() => {
      const aiMsg: Msg = { id: (Date.now()+1).toString(), role:"ai", text: getResp(), time: now() };
      setMsgs(prev => [...prev, aiMsg]);
      setLoading(false);
    }, delay);
  };

  const reset = () => { setMsgs([]); setInput(""); };

  const panelW = expanded ? "w-[520px]" : "w-[360px]";
  const panelH = expanded ? "h-[620px]" : "h-[480px]";

  return (
    <div className="fixed bottom-6 right-6 z-[1000] flex flex-col items-end gap-3 pointer-events-none">

      {/* в”Ђв”Ђ Chat Panel в”Ђв”Ђ */}
      {open && (
        <div
          className={`pointer-events-auto flex flex-col ${panelW} ${panelH} rounded-3xl overflow-hidden transition-all duration-300`}
          style={{
            background: "#fff",
            boxShadow: "0 32px 80px rgba(37,99,235,0.22), 0 8px 32px rgba(13,148,136,0.15), 0 0 0 1px rgba(37,99,235,0.08)",
          }}
        >
          {/* Header */}
          <div
            className="flex-shrink-0 px-4 py-3 flex items-center gap-3"
            style={{ background: "linear-gradient(135deg, #1d4ed8 0%, #0d9488 100%)" }}
          >
            {/* Logo orb */}
            <div className="relative flex-shrink-0">
              <div className="size-9 rounded-2xl bg-white/20 flex items-center justify-center backdrop-blur-sm">
                <Sparkles className="size-5 text-white" />
              </div>
              <span className="absolute -top-1 -right-1 size-3 rounded-full bg-emerald-400 border-2 border-white animate-pulse" />
            </div>

            <div className="flex-1 min-w-0">
              <div className="flex items-center gap-2">
                <p className="text-sm text-white tracking-wide">ZENITH AI</p>
                <span className="px-1.5 py-0.5 rounded-full bg-white/20 text-white text-[9px] tracking-widest">PRO</span>
              </div>
              <p className="text-[10px] text-white/70">AI РђСЃРёСЃС‚РµРЅС‚ В· РЎРљ РЎС‚СЂРѕР№ Р•РћРћР”</p>
            </div>

            <div className="flex items-center gap-1">
              <button onClick={reset} title="РќРѕРІ СЂР°Р·РіРѕРІРѕСЂ"
                className="size-8 flex items-center justify-center rounded-xl text-white/70 hover:bg-white/20 hover:text-white transition-all">
                <RotateCcw className="size-3.5" />
              </button>
              <button onClick={() => setExpanded(e => !e)} title={expanded ? "РЎРІРёР№" : "Р Р°Р·С€РёСЂРё"}
                className="size-8 flex items-center justify-center rounded-xl text-white/70 hover:bg-white/20 hover:text-white transition-all">
                {expanded ? <Minimize2 className="size-3.5" /> : <Maximize2 className="size-3.5" />}
              </button>
              <button onClick={() => setOpen(false)}
                className="size-8 flex items-center justify-center rounded-xl text-white/70 hover:bg-white/20 hover:text-white transition-all">
                <ChevronDown className="size-4" />
              </button>
            </div>
          </div>

          {/* Messages */}
          <div className="flex-1 overflow-y-auto px-4 py-3 space-y-3 bg-gradient-to-b from-blue-50/40 to-white">

            {msgs.length === 0 && (
              <>
                {/* Welcome */}
                <div className="flex gap-2.5 items-start">
                  <div className="size-7 rounded-xl flex-shrink-0 mt-0.5 flex items-center justify-center"
                    style={{ background:"linear-gradient(135deg,#2563EB,#0D9488)" }}>
                    <Bot className="size-3.5 text-white" />
                  </div>
                  <div className="bg-white rounded-2xl rounded-tl-sm px-3.5 py-2.5 shadow-sm border border-gray-100 max-w-[85%]">
                    <p className="text-sm text-gray-700 leading-relaxed">
                      Р—РґСЂР°РІРµР№! РђР· СЃСЉРј <strong>ZENITH</strong> вЂ” С‚РІРѕСЏС‚ СЃС‚СЂРѕРёС‚РµР»РµРЅ AI. РџРёС‚Р°Р№ РјРµ Р·Р° РїСЂРѕРµРєС‚Рё, РґРѕРіРѕРІРѕСЂРё, С„РёРЅР°РЅСЃРё РёР»Рё РІСЃРёС‡РєРѕ РґСЂСѓРіРѕ. рџЏ—пёЏ
                    </p>
                  </div>
                </div>

                {/* Quick prompts */}
                <div className="grid grid-cols-2 gap-1.5 pt-1">
                  {QUICK.map(q => (
                    <button key={q} onClick={() => send(q)}
                      className="text-left px-3 py-2 rounded-xl bg-white border border-gray-100 text-xs text-gray-600 hover:border-blue-300 hover:text-blue-700 hover:bg-blue-50 transition-all shadow-sm">
                      {q}
                    </button>
                  ))}
                </div>
              </>
            )}

            {msgs.map(msg => (
              <div key={msg.id} className={`flex gap-2.5 items-end ${msg.role==="user" ? "flex-row-reverse" : ""}`}>
                <div className={`size-6 rounded-xl flex-shrink-0 flex items-center justify-center text-[10px] text-white ${
                  msg.role==="ai"
                    ? ""
                    : "bg-gradient-to-br from-violet-500 to-blue-600"
                }`}
                  style={msg.role==="ai" ? { background:"linear-gradient(135deg,#2563EB,#0D9488)" } : {}}>
                  {msg.role==="ai" ? <Bot className="size-3.5" /> : "РЎРЎ"}
                </div>
                <div className={`max-w-[78%] ${msg.role==="user" ? "items-end" : "items-start"} flex flex-col gap-0.5`}>
                  <div className={`px-3.5 py-2.5 rounded-2xl text-sm leading-relaxed ${
                    msg.role==="user"
                      ? "text-white rounded-br-sm"
                      : "bg-white text-gray-700 rounded-bl-sm shadow-sm border border-gray-100"
                  }`}
                    style={msg.role==="user" ? { background:"linear-gradient(135deg,#2563EB,#0D9488)" } : {}}>
                    {formatText(msg.text)}
                  </div>
                  {msg.role==="ai" && (
                    <div className="flex items-center gap-1 px-1">
                      <button className="size-5 flex items-center justify-center text-gray-300 hover:text-blue-500 transition-colors"><Copy className="size-3" /></button>
                      <button className="size-5 flex items-center justify-center text-gray-300 hover:text-emerald-500 transition-colors"><ThumbsUp className="size-3" /></button>
                    </div>
                  )}
                </div>
              </div>
            ))}

            {/* Typing indicator */}
            {loading && (
              <div className="flex gap-2.5 items-end">
                <div className="size-6 rounded-xl flex-shrink-0 flex items-center justify-center"
                  style={{ background:"linear-gradient(135deg,#2563EB,#0D9488)" }}>
                  <Bot className="size-3.5 text-white" />
                </div>
                <div className="bg-white rounded-2xl rounded-bl-sm px-4 py-3 shadow-sm border border-gray-100">
                  <div className="flex gap-1.5 items-center">
                    {[0,1,2].map(i => (
                      <div key={i} className="size-1.5 rounded-full bg-blue-400 animate-bounce"
                        style={{ animationDelay:`${i*0.18}s` }} />
                    ))}
                    <span className="text-xs text-gray-400 ml-1">ZENITH Р°РЅР°Р»РёР·РёСЂР°...</span>
                  </div>
                </div>
              </div>
            )}
            <div ref={endRef} />
          </div>

          {/* Voice transcript */}
          {listening && (
            <div className="px-4 py-2 bg-red-50 border-t border-red-100 flex items-center gap-2">
              <div className="flex gap-0.5">
                {[...Array(5)].map((_,i) => (
                  <div key={i} className="w-1 rounded-full bg-red-500 animate-pulse"
                    style={{ height: 8 + Math.sin(i)*6, animationDelay:`${i*0.1}s` }} />
                ))}
              </div>
              <p className="text-xs text-red-600 flex-1 truncate">{transcript || "РЎР»СѓС€Р°Рј..."}</p>
              <button onClick={stopListening} className="text-xs text-red-500 hover:text-red-700">РЎС‚РѕРї</button>
            </div>
          )}

          {/* Input */}
          <div className="flex-shrink-0 px-3 pb-3 pt-2 bg-white border-t border-gray-100">
            <div className="flex items-center gap-2 bg-gray-50 rounded-2xl border border-gray-200 px-3 py-2 focus-within:ring-2 focus-within:ring-blue-500/20 focus-within:border-blue-400 transition-all">
              <button className="text-gray-400 hover:text-gray-600 transition-colors flex-shrink-0">
                <Paperclip className="size-3.5" />
              </button>
              <input
                value={input}
                onChange={e => setInput(e.target.value)}
                onKeyDown={e => e.key==="Enter" && !e.shiftKey && send()}
                placeholder="РџРёС‚Р°Р№ ZENITH AI..."
                className="flex-1 bg-transparent text-sm text-gray-700 placeholder-gray-400 focus:outline-none"
              />
              {/* Voice button */}
              <button
                onMouseDown={startListening}
                onMouseUp={stopListening}
                onTouchStart={startListening}
                onTouchEnd={stopListening}
                className={`size-8 flex items-center justify-center rounded-xl transition-all flex-shrink-0 ${
                  listening
                    ? "bg-red-500 text-white shadow-md shadow-red-300 scale-110"
                    : "text-gray-400 hover:bg-blue-50 hover:text-blue-600"
                }`}
              >
                {listening ? <MicOff className="size-3.5" /> : <Mic className="size-3.5" />}
              </button>
              {/* Send button */}
              <button
                onClick={() => send()}
                disabled={!input.trim() || loading}
                className="size-8 flex items-center justify-center rounded-xl text-white transition-all active:scale-95 flex-shrink-0 disabled:opacity-40 disabled:cursor-not-allowed"
                style={{ background: "linear-gradient(135deg,#2563EB,#0D9488)" }}
              >
                <Send className="size-3.5" />
              </button>
            </div>
          </div>
        </div>
      )}

      {/* в”Ђв”Ђ Floating Trigger Button в”Ђв”Ђ */}
      <div className="pointer-events-auto relative">
        {/* Outer pulse rings */}
        {!open && (
          <>
            <div className={`absolute inset-0 rounded-full transition-all duration-1000 ${pulseRing ? "scale-150 opacity-0" : "scale-100 opacity-0"}`}
              style={{ background:"linear-gradient(135deg,#2563EB,#0D9488)", transition:"transform 1s ease-out, opacity 1s ease-out" }} />
            <div className="absolute -inset-2 rounded-full animate-ping opacity-20"
              style={{ background:"linear-gradient(135deg,#2563EB,#0D9488)", animationDuration:"3s" }} />
            <div className="absolute -inset-1 rounded-full animate-ping opacity-10"
              style={{ background:"linear-gradient(135deg,#2563EB,#0D9488)", animationDuration:"2s", animationDelay:"0.5s" }} />
          </>
        )}

        <button
          onClick={() => setOpen(o => !o)}
          className="relative flex items-center gap-0 rounded-full transition-all duration-300 active:scale-95 group overflow-hidden"
          style={{
            background: open
              ? "linear-gradient(135deg,#1e3a8a,#0f766e)"
              : "linear-gradient(135deg,#2563EB 0%,#0D9488 100%)",
            boxShadow: open
              ? "0 8px 32px rgba(37,99,235,0.4)"
              : "0 12px 40px rgba(37,99,235,0.45), 0 4px 16px rgba(13,148,136,0.3), inset 0 1px 0 rgba(255,255,255,0.2)",
            height: 60,
            paddingLeft: 20,
            paddingRight: 20,
          }}
        >
          {/* Shimmer overlay */}
          {!open && (
            <div className="absolute inset-0 opacity-0 group-hover:opacity-100 transition-opacity duration-300"
              style={{ background:"linear-gradient(135deg,rgba(255,255,255,0.15),transparent)" }} />
          )}

          {/* Icon */}
          <div className="relative flex-shrink-0">
            {open
              ? <X className="size-5 text-white" />
              : (
                <div className="relative">
                  <Sparkles className="size-6 text-white drop-shadow-sm" />
                  {/* green dot */}
                  <span className="absolute -top-0.5 -right-0.5 size-2.5 rounded-full bg-emerald-400 border-2 border-white" />
                </div>
              )
            }
          </div>

          {/* Label (only when closed) */}
          {!open && (
            <div className="ml-3 flex flex-col items-start">
              <span className="text-white text-sm leading-tight tracking-wide">ZENITH AI</span>
              <span className="text-white/70 text-[10px] leading-tight tracking-widest uppercase">РђСЃРёСЃС‚РµРЅС‚</span>
            </div>
          )}

          {/* Voice indicator on trigger */}
          {!open && (
            <div className="ml-3 flex items-center gap-0.5">
              {[...Array(3)].map((_,i) => (
                <div key={i} className="w-0.5 rounded-full bg-white/50 animate-pulse"
                  style={{ height: 10 + i*4, animationDelay:`${i*0.2}s`, animationDuration:"1.2s" }} />
              ))}
            </div>
          )}
        </button>

        {/* Mic shortcut (separate button when panel is closed) */}
        {!open && (
          <button
            onMouseDown={e => { e.stopPropagation(); setOpen(true); setTimeout(startListening, 100); }}
            onTouchStart={e => { e.stopPropagation(); setOpen(true); setTimeout(startListening, 100); }}
            className="absolute -top-3 -right-3 size-9 rounded-full flex items-center justify-center transition-all hover:scale-110 active:scale-95"
            style={{
              background: listening ? "#ef4444" : "linear-gradient(135deg,#7c3aed,#2563EB)",
              boxShadow: listening
                ? "0 4px 16px rgba(239,68,68,0.5)"
                : "0 4px 16px rgba(124,58,237,0.4)",
            }}
            title="Р“РѕРІРѕСЂРё СЃ ZENITH"
          >
            <Mic className="size-4 text-white" />
          </button>
        )}
      </div>
    </div>
  );
}

// в”Ђв”Ђв”Ђ Helpers в”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђ
function now() {
  return new Date().toLocaleTimeString("bg-BG", { hour:"2-digit", minute:"2-digit" });
}

function formatText(text: string) {
  return text.split("\n").map((line, i) => {
    const parts = line.split(/\*\*(.*?)\*\*/g);
    return (
      <span key={i} className="block">
        {parts.map((p, j) => j % 2 === 1 ? <strong key={j}>{p}</strong> : p)}
      </span>
    );
  });
}



// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ
// FILE: src/app/components/ClientShell.tsx
// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ

import { useState, useMemo } from "react";
import { Link, NavLink, Outlet, useNavigate } from "react-router";
import {
  Home, Wand2, FolderKanban, Play, MessageSquare,
  ShoppingBag, FileText, Settings, LogOut, Plus,
  Menu, X, Search, ChevronRight,
} from "lucide-react";
import { TemaDomLogo } from "./TemaDomLogo";

// в”Ђв”Ђв”Ђ Nav items в”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђ
const NAV_ITEMS = [
  { label: "РќР°С‡Р°Р»Рѕ",          icon: Home,          to: "/client",              end: true  },
  { label: "РќРѕРІ РїСЂРѕРµРєС‚",      icon: Wand2,         to: "/client/project-wizard"           },
  { label: "РњРѕРёС‚Рµ РїСЂРѕРµРєС‚Рё",   icon: FolderKanban,  to: "/client/projects"                 },
  // в”Ђв”Ђ separator here в”Ђв”Ђ
  { label: "Zclips",          icon: Play,          to: "/community"                        },
  { label: "Р§Р°С‚РѕРІРµ",          icon: MessageSquare, to: "/client/chat"                      },
  { label: "РџР°Р·Р°СЂ",           icon: ShoppingBag,   to: "/client/marketplace"               },
  { label: "Р”РѕРєСѓРјРµРЅС‚Рё",       icon: FileText,      to: "/client/documents"                 },
  { label: "РќР°СЃС‚СЂРѕР№РєРё",       icon: Settings,      to: "/client/settings"                  },
];

const SEPARATOR_AFTER = 2; // 0-indexed вЂ” after index 2 = "РњРѕРёС‚Рµ РїСЂРѕРµРєС‚Рё"

const USER = { name: "РРІР°РЅ РџРµС‚СЂРѕРІ", initials: "РРџ" };

// в”Ђв”Ђв”Ђ Sidebar content в”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђ
function SidebarContent({ onClose }: { onClose?: () => void }) {
  const [search, setSearch] = useState("");
  const navigate = useNavigate();

  const filtered = useMemo(
    () =>
      NAV_ITEMS.filter((item) =>
        item.label.toLowerCase().includes(search.toLowerCase())
      ),
    [search]
  );

  const handleLogout = () => {
    navigate("/login");
  };

  return (
    <div className="flex flex-col h-full">
      {/* в”Ђв”Ђ Logo row в”Ђв”Ђ */}
      <div className="flex items-center justify-between px-5 py-5 border-b border-gray-100">
        <Link to="/" onClick={onClose}>
          <TemaDomLogo size="sm" instanceId="client-sidebar" />
        </Link>
        {onClose && (
          <button
            onClick={onClose}
            className="size-8 flex items-center justify-center rounded-lg text-gray-400 hover:bg-gray-100 hover:text-gray-700 transition-colors lg:hidden"
            aria-label="Р—Р°С‚РІРѕСЂРё РјРµРЅСЋС‚Рѕ"
          >
            <X className="size-5" />
          </button>
        )}
      </div>

      {/* в”Ђв”Ђ Search в”Ђв”Ђ */}
      <div className="px-4 pt-4 pb-2">
        <div className="relative">
          <Search className="absolute left-3 top-1/2 -translate-y-1/2 size-3.5 text-gray-400 pointer-events-none" />
          <input
            type="text"
            placeholder="РўСЉСЂСЃРё РІ РјРµРЅСЋС‚РѕвЂ¦"
            value={search}
            onChange={(e) => setSearch(e.target.value)}
            className="w-full pl-8 pr-3 py-2 text-xs bg-gray-50 border border-gray-200 rounded-xl text-gray-700 placeholder-gray-400 focus:outline-none focus:ring-2 focus:ring-blue-500/20 focus:border-blue-400 transition-all"
          />
        </div>
      </div>

      {/* в”Ђв”Ђ Nav links в”Ђв”Ђ */}
      <nav className="flex-1 px-3 py-2 overflow-y-auto">
        {search
          ? /* Filtered results */
            filtered.length === 0 ? (
              <p className="text-xs text-gray-400 text-center py-6">РќСЏРјР° СЂРµР·СѓР»С‚Р°С‚Рё</p>
            ) : (
              filtered.map((item) => (
                <NavItem key={item.to} item={item} onClose={onClose} />
              ))
            )
          : /* Full list with separator */
            NAV_ITEMS.map((item, idx) => (
              <div key={item.to}>
                {idx === SEPARATOR_AFTER + 1 && (
                  <div className="my-2 mx-1 border-t border-gray-100" />
                )}
                <NavItem item={item} onClose={onClose} />
              </div>
            ))}
      </nav>

      {/* в”Ђв”Ђ User + Logout в”Ђв”Ђ */}
      <div className="px-4 py-4 border-t border-gray-100">
        <div className="flex items-center gap-3 mb-3 px-1">
          <div className="size-8 rounded-full bg-gradient-to-br from-blue-500 to-teal-500 flex items-center justify-center text-white text-xs font-semibold flex-shrink-0">
            {USER.initials}
          </div>
          <div className="min-w-0">
            <p className="text-sm text-gray-800 truncate">{USER.name}</p>
            <p className="text-xs text-gray-400">РљР»РёРµРЅС‚СЃРєРё Р°РєР°СѓРЅС‚</p>
          </div>
        </div>
        <button
          onClick={handleLogout}
          className="w-full flex items-center gap-2.5 px-3 py-2.5 rounded-xl text-red-500 hover:bg-red-50 hover:text-red-600 transition-all group"
        >
          <LogOut className="size-4 flex-shrink-0 group-hover:-translate-x-0.5 transition-transform" />
          <span className="text-sm">РР·С…РѕРґ</span>
        </button>
      </div>
    </div>
  );
}

// в”Ђв”Ђв”Ђ Single nav item в”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђ
function NavItem({
  item,
  onClose,
}: {
  item: (typeof NAV_ITEMS)[0];
  onClose?: () => void;
}) {
  const Icon = item.icon;
  return (
    <NavLink
      to={item.to}
      end={item.end}
      onClick={onClose}
      className={({ isActive }) =>
        `flex items-center gap-3 px-3 py-2.5 rounded-xl mb-0.5 transition-all group ${
          isActive
            ? "bg-blue-50 text-blue-700"
            : "text-gray-600 hover:bg-gray-100 hover:text-gray-900"
        }`
      }
    >
      {({ isActive }) => (
        <>
          <Icon
            className={`size-4 flex-shrink-0 transition-transform group-hover:scale-110 ${
              isActive ? "text-blue-600" : "text-gray-400 group-hover:text-gray-700"
            }`}
          />
          <span className={`text-sm flex-1 ${isActive ? "font-medium" : ""}`}>
            {item.label}
          </span>
          {isActive && (
            <ChevronRight className="size-3.5 text-blue-400" />
          )}
        </>
      )}
    </NavLink>
  );
}

// в”Ђв”Ђв”Ђ Main Shell в”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”ЂпїЅпїЅв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђ
export function ClientShell({ children }: { children?: React.ReactNode }) {
  const [mobileOpen, setMobileOpen] = useState(false);
  const navigate = useNavigate();

  return (
    <div className="flex h-screen bg-gray-50 overflow-hidden">
      {/* в”Ђв”Ђ Desktop sidebar в”Ђв”Ђ */}
      <aside className="hidden lg:flex flex-col w-64 bg-white border-r border-gray-100 flex-shrink-0">
        <SidebarContent />
      </aside>

      {/* в”Ђв”Ђ Mobile overlay в”Ђв”Ђ */}
      {mobileOpen && (
        <div className="lg:hidden fixed inset-0 z-50 flex">
          {/* Backdrop */}
          <div
            className="absolute inset-0 bg-black/40 backdrop-blur-sm"
            onClick={() => setMobileOpen(false)}
          />
          {/* Drawer */}
          <aside className="relative z-10 w-72 bg-white h-full shadow-2xl flex flex-col">
            <SidebarContent onClose={() => setMobileOpen(false)} />
          </aside>
        </div>
      )}

      {/* в”Ђв”Ђ Main area в”Ђв”Ђ */}
      <div className="flex-1 flex flex-col min-w-0 overflow-hidden">
        {/* в”Ђв”Ђ Header пїЅпїЅпїЅв”Ђ */}
        <header className="h-16 bg-white border-b border-gray-100 flex items-center px-4 lg:px-6 gap-3 flex-shrink-0">
          {/* Hamburger (mobile) */}
          <button
            onClick={() => setMobileOpen(true)}
            className="lg:hidden size-9 flex items-center justify-center rounded-xl text-gray-500 hover:bg-gray-100 transition-colors"
            aria-label="РћС‚РІРѕСЂРё РјРµРЅСЋС‚Рѕ"
          >
            <Menu className="size-5" />
          </button>

          {/* Logo (mobile only вЂ” desktop shows in sidebar) */}
          <Link to="/" className="lg:hidden">
            <TemaDomLogo size="sm" instanceId="client-header-mob" />
          </Link>

          {/* Badge */}
          <div className="hidden sm:flex items-center gap-2 px-3 py-1.5 rounded-full bg-blue-50 border border-blue-100">
            <span className="size-1.5 rounded-full bg-blue-500 animate-pulse" />
            <span className="text-xs text-blue-700 tracking-wide">РљР›РР•РќРўРЎРљР Р¦Р•РќРўРЄР </span>
          </div>

          {/* Spacer */}
          <div className="flex-1" />

          {/* + РќРѕРІ РїСЂРѕРµРєС‚ */}
          <button
            onClick={() => navigate("/client/project-wizard")}
            className="flex items-center gap-1.5 px-3 py-2 rounded-xl bg-blue-600 hover:bg-blue-700 text-white text-sm transition-all shadow-sm shadow-blue-200 active:scale-95"
            aria-label="РќРѕРІ РїСЂРѕРµРєС‚"
          >
            <Plus className="size-4" />
            <span className="hidden sm:inline">РќРѕРІ РїСЂРѕРµРєС‚</span>
          </button>

          {/* Avatar */}
          <button
            onClick={() => navigate("/client/settings")}
            className="size-9 rounded-full bg-gradient-to-br from-blue-500 to-teal-500 flex items-center justify-center text-white text-sm font-semibold hover:scale-105 transition-transform shadow-sm flex-shrink-0"
            aria-label="РќР°СЃС‚СЂРѕР№РєРё РЅР° РїСЂРѕС„РёР»Р°"
          >
            {USER.initials}
          </button>
        </header>

        {/* в”Ђв”Ђ Page content в”Ђв”Ђ */}
        <main className="flex-1 overflow-y-auto">
          {children ?? <Outlet />}
        </main>
      </div>
    </div>
  );
}


// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ
// FILE: src/app/components/TemaDomLogo.tsx
// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ

interface TemaDomLogoProps {
  size?: "sm" | "md" | "lg";
  variant?: "default" | "white";
  instanceId?: string;
}

export function TemaDomLogo({
  size = "md",
  variant = "default",
  instanceId = "a",
}: TemaDomLogoProps) {
  const iconSize = size === "sm" ? 32 : size === "lg" ? 48 : 38;
  const textClass =
    size === "sm"
      ? "text-lg"
      : size === "lg"
      ? "text-2xl"
      : "text-xl";
  const gradId = `tdGrad-${instanceId}`;
  const gradId2 = `tdGrad2-${instanceId}`;
  const clipId = `tdClip-${instanceId}`;

  const textStyle =
    variant === "white"
      ? { color: "white" }
      : {
          background: "linear-gradient(135deg, #1d4ed8 0%, #0f766e 100%)",
          WebkitBackgroundClip: "text" as const,
          WebkitTextFillColor: "transparent" as const,
          backgroundClip: "text" as const,
        };

  return (
    <div className="flex items-center gap-2.5 select-none">
      <svg
        width={iconSize}
        height={iconSize}
        viewBox="0 0 40 40"
        fill="none"
        xmlns="http://www.w3.org/2000/svg"
        aria-label="TemaDom logo icon"
      >
        <defs>
          <linearGradient
            id={gradId}
            x1="0"
            y1="0"
            x2="40"
            y2="40"
            gradientUnits="userSpaceOnUse"
          >
            <stop offset="0%" stopColor="#2563EB" />
            <stop offset="100%" stopColor="#0D9488" />
          </linearGradient>
          <linearGradient
            id={gradId2}
            x1="0"
            y1="0"
            x2="40"
            y2="20"
            gradientUnits="userSpaceOnUse"
          >
            <stop offset="0%" stopColor="#3B82F6" />
            <stop offset="100%" stopColor="#14B8A6" />
          </linearGradient>
          <clipPath id={clipId}>
            <rect width="40" height="40" rx="10" />
          </clipPath>
        </defs>

        {/* Background */}
        <rect width="40" height="40" rx="10" fill={`url(#${gradId})`} />

        {/* Subtle inner glow */}
        <rect
          width="40"
          height="40"
          rx="10"
          fill="white"
          fillOpacity="0.06"
        />

        {/* House / building shape */}
        <g clipPath={`url(#${clipId})`}>
          {/* Roof */}
          <path
            d="M20 7L32 17.5H28.5V32H11.5V17.5H8L20 7Z"
            fill="white"
            fillOpacity="0.95"
          />
          {/* Door */}
          <rect
            x="16.5"
            y="24"
            width="7"
            height="8"
            rx="1.5"
            fill={`url(#${gradId})`}
            fillOpacity="0.55"
          />
          {/* Window left */}
          <rect
            x="13"
            y="20"
            width="4.5"
            height="4"
            rx="1"
            fill={`url(#${gradId})`}
            fillOpacity="0.4"
          />
          {/* Window right */}
          <rect
            x="22.5"
            y="20"
            width="4.5"
            height="4"
            rx="1"
            fill={`url(#${gradId})`}
            fillOpacity="0.4"
          />
        </g>

        {/* AI spark вЂ” top right accent dot */}
        <circle cx="31" cy="8" r="3" fill="white" fillOpacity="0.9" />
        <circle cx="31" cy="8" r="1.5" fill={`url(#${gradId2})`} />

        {/* Small accent dots (neural/AI feel) */}
        <circle cx="27" cy="5" r="1.2" fill="white" fillOpacity="0.45" />
        <circle cx="34" cy="12" r="1.2" fill="white" fillOpacity="0.45" />
      </svg>

      <span
        className={`${textClass} font-semibold tracking-tight`}
        style={textStyle}
      >
        Tema<span style={{ fontWeight: 700 }}>Dom</span>
      </span>
    </div>
  );
}



// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ
// FILE: src/app/pages/pro/ProDashboard.tsx
// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ

import { useState } from "react";
import { Link, useNavigate } from "react-router";
import {
  TrendingUp, TrendingDown, Calculator, FileText, Users, Bot,
  Plus, ArrowRight, ChevronRight, Clock, CheckCircle2, AlertCircle,
  Euro, BarChart3, Zap, Star, Building2, Crown, Sparkles,
  Send, Eye, MoreHorizontal, Bell,
} from "lucide-react";

// в”Ђв”Ђв”Ђ Mock data в”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђ
const STATS = [
  {
    label: "РџСЂРёС…РѕРґРё (РјРµСЃРµС†)",
    value: "38 450 Р»РІ",
    change: "+12%",
    up: true,
    icon: Euro,
    color: "text-emerald-600",
    bg: "bg-emerald-50",
    border: "border-emerald-100",
  },
  {
    label: "РђРєС‚РёРІРЅРё РїСЂРѕРµРєС‚Рё",
    value: "14",
    change: "+3",
    up: true,
    icon: Building2,
    color: "text-blue-600",
    bg: "bg-blue-50",
    border: "border-blue-100",
  },
  {
    label: "РљРЎРЎ РіРµРЅРµСЂРёСЂР°РЅРё",
    value: "27",
    change: "С‚Р°Р·Рё СЃРµРґРјРёС†Р°",
    up: true,
    icon: Calculator,
    color: "text-teal-600",
    bg: "bg-teal-50",
    border: "border-teal-100",
  },
  {
    label: "Р•РєРёРї",
    value: "8",
    change: "Р°РєС‚РёРІРЅРё",
    up: true,
    icon: Users,
    color: "text-violet-600",
    bg: "bg-violet-50",
    border: "border-violet-100",
  },
];

const PROJECTS = [
  {
    id: 1,
    name: "Р РµРјРѕРЅС‚ Р°РїР°СЂС‚Р°РјРµРЅС‚ вЂ” СѓР». Р’РёС‚РѕС€Р° 24",
    client: "РњР°СЂРёСЏ РРІР°РЅРѕРІР°",
    value: "12 400 Р»РІ",
    progress: 72,
    status: "active",
    eta: "18 Р°РїСЂ",
    team: ["Р“РЎ", "РџР”"],
  },
  {
    id: 2,
    name: "РЎС‚СЂРѕРµР¶ РІРёР»Р° вЂ” СЃ. Р“РµСЂРјР°РЅ",
    client: "РџРµС‚СЂРѕРІ & РЎРёРЅРѕРІРµ",
    value: "87 200 Р»РІ",
    progress: 34,
    status: "active",
    eta: "30 СЋРЅРё",
    team: ["РњРљ", "РЎРў", "РР’"],
  },
  {
    id: 3,
    name: "РћС„РёСЃ СЂРµРјРѕРЅС‚ вЂ” Р±СѓР». РҐСЂРёСЃС‚Рѕ Р‘РѕС‚РµРІ",
    client: "Tech Soft OOD",
    value: "24 900 Р»РІ",
    progress: 90,
    status: "finishing",
    eta: "10 Р°РїСЂ",
    team: ["Р“РЎ"],
  },
  {
    id: 4,
    name: "Р‘РѕСЏРґРёСЃРІР°РЅРµ Р¶РёР»РёС‰РµРЅ Р±Р»РѕРє",
    client: "Р•РЎ РР·С‚РѕРє",
    value: "8 700 Р»РІ",
    progress: 10,
    status: "pending",
    eta: "РњР°Р№",
    team: ["РџР”", "РњРљ"],
  },
];

const AI_ACTIONS = [
  { icon: Calculator, label: "Р“РµРЅРµСЂРёСЂР°Р№ РљРЎРЎ", sub: "РќРѕРІР° РєРѕР»РёС‡РµСЃС‚РІРµРЅР° СЃРјРµС‚РєР°", to: "/pro/kss", color: "text-blue-600", bg: "bg-blue-50" },
  { icon: FileText,   label: "РќРѕРІ РґРѕРіРѕРІРѕСЂ",   sub: "AI РґРѕРіРѕРІРѕСЂ Р·Р° РїСЂРѕРµРєС‚",     to: "/pro/contracts", color: "text-teal-600", bg: "bg-teal-50" },
  { icon: BarChart3,  label: "РђРЅР°Р»РёР·",         sub: "Р¤РёРЅР°РЅСЃРѕРІ РїСЂРµРіР»РµРґ",          to: "/pro/analytics", color: "text-violet-600", bg: "bg-violet-50" },
  { icon: Users,      label: "РЈРїСЂР°РІР»РµРЅРёРµ РµРєРёРї", sub: "Р Р°Р·РїСЂРµРґРµР»Рё Р·Р°РґР°С‡Рё",        to: "/pro/team", color: "text-amber-600", bg: "bg-amber-50" },
];

const NOTIFICATIONS = [
  { icon: CheckCircle2, color: "text-emerald-500", text: "РљРЎРЎ #127 вЂ” РѕРґРѕР±СЂРµРЅР° РѕС‚ РєР»РёРµРЅС‚Р°", time: "2РјРёРЅ" },
  { icon: AlertCircle,  color: "text-amber-500",   text: "РџСЂРѕРµРєС‚ Р“РµСЂРјР°РЅ вЂ” РґРѕСЃС‚Р°РІРєР° Р·Р°РєСЉСЃРЅСЏРІР°", time: "15РјРёРЅ" },
  { icon: Bell,         color: "text-blue-500",     text: "РќРѕРІР° РѕС„РµСЂС‚Р° вЂ” СѓР». РћРїСЉР»С‡РµРЅСЃРєР° 44", time: "1С‡" },
  { icon: Star,         color: "text-violet-500",   text: "РќРѕРІР° РѕС†РµРЅРєР° 5в… РѕС‚ РњР°СЂРёСЏ РРІР°РЅРѕРІР°", time: "3С‡" },
];

const STATUS_MAP: Record<string, { label: string; color: string; bg: string; icon: typeof CheckCircle2 }> = {
  active:    { label: "РђРєС‚РёРІРµРЅ",    color: "text-blue-700",    bg: "bg-blue-50",    icon: Clock },
  finishing: { label: "Р¤РёРЅР°Р»РёР·РёСЂР°", color: "text-emerald-700", bg: "bg-emerald-50", icon: CheckCircle2 },
  pending:   { label: "РџСЂРµРґСЃС‚РѕРё",   color: "text-amber-700",   bg: "bg-amber-50",   icon: AlertCircle },
};

// в”Ђв”Ђв”Ђ Components в”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђ
function StatCard({ stat }: { stat: typeof STATS[0] }) {
  const Icon = stat.icon;
  return (
    <div className={`bg-white rounded-2xl border ${stat.border} p-5 flex flex-col gap-3 hover:shadow-md transition-all`}>
      <div className="flex items-center justify-between">
        <div className={`size-10 rounded-xl ${stat.bg} flex items-center justify-center`}>
          <Icon className={`size-5 ${stat.color}`} />
        </div>
        <span className={`text-xs px-2 py-0.5 rounded-full ${stat.up ? "bg-emerald-50 text-emerald-600" : "bg-red-50 text-red-600"}`}>
          {stat.change}
        </span>
      </div>
      <div>
        <p className="text-2xl text-gray-800">{stat.value}</p>
        <p className="text-xs text-gray-500 mt-0.5">{stat.label}</p>
      </div>
    </div>
  );
}

function ProjectRow({ proj }: { proj: typeof PROJECTS[0] }) {
  const s = STATUS_MAP[proj.status];
  const SIcon = s.icon;
  return (
    <div className="flex items-center gap-4 py-3.5 border-b border-gray-50 last:border-0 group hover:bg-gray-50/60 px-1 rounded-xl transition-colors cursor-pointer">
      <div className="flex-1 min-w-0">
        <p className="text-sm text-gray-800 truncate">{proj.name}</p>
        <p className="text-xs text-gray-400 mt-0.5">{proj.client}</p>
      </div>
      <div className="hidden sm:block w-28">
        <div className="flex items-center gap-1.5 mb-1">
          <div className="flex-1 h-1.5 bg-gray-100 rounded-full overflow-hidden">
            <div
              className="h-full rounded-full bg-gradient-to-r from-blue-500 to-teal-500 transition-all"
              style={{ width: `${proj.progress}%` }}
            />
          </div>
          <span className="text-xs text-gray-400 w-8 text-right">{proj.progress}%</span>
        </div>
      </div>
      <div className="hidden md:flex items-center gap-1">
        {proj.team.slice(0, 3).map((m, i) => (
          <div key={i} className="size-6 rounded-full bg-gradient-to-br from-blue-400 to-teal-400 flex items-center justify-center text-white text-[9px] -ml-1 first:ml-0 border border-white">
            {m}
          </div>
        ))}
      </div>
      <span className="hidden lg:block text-xs text-gray-500 w-16 text-right">{proj.eta}</span>
      <span className={`flex items-center gap-1 px-2 py-1 rounded-full text-xs ${s.bg} ${s.color}`}>
        <SIcon className="size-3" />
        {s.label}
      </span>
      <span className="text-sm text-gray-800 w-24 text-right hidden sm:block">{proj.value}</span>
      <ChevronRight className="size-4 text-gray-300 group-hover:text-gray-500 transition-colors flex-shrink-0" />
    </div>
  );
}

// в”Ђв”Ђв”Ђ Main в”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђ
export function ProDashboard() {
  const [aiInput, setAiInput] = useState("");
  const navigate = useNavigate();

  return (
    <div className="p-5 lg:p-7 space-y-7 max-w-[1400px] mx-auto">

      {/* в”Ђв”Ђ Welcome header в”Ђв”Ђ */}
      <div className="flex flex-col sm:flex-row sm:items-center justify-between gap-4">
        <div>
          <div className="flex items-center gap-2 mb-1">
            <Crown className="size-4 text-amber-500" />
            <span className="text-xs text-amber-600">РЎРљ РЎС‚СЂР№ Р•РћРћР” В· РџСЂРµРјРёСѓРј AI</span>
          </div>
          <h1 className="text-2xl text-gray-800">Р”РѕР±СЂРµ РґРѕС€Р»Рё, РЎС‚РѕСЏРЅ рџ‘‹</h1>
          <p className="text-sm text-gray-500 mt-0.5">РРјР°С‚Рµ 3 РїСЂРѕРµРєС‚Р° СЃ РїСЂРµРґСЃС‚РѕСЏС‰Рё СЃСЂРѕРєРѕРІРµ С‚Р°Р·Рё СЃРµРґРјРёС†Р°</p>
        </div>
        <div className="flex items-center gap-2">
          <button
            onClick={() => navigate("/pro/kss")}
            className="flex items-center gap-2 px-4 py-2.5 rounded-xl border border-gray-200 text-gray-700 text-sm hover:bg-gray-50 transition-all"
          >
            <Calculator className="size-4" />
            РќРѕРІР° РљРЎРЎ
          </button>
          <button
            onClick={() => navigate("/pro/ai")}
            className="flex items-center gap-2 px-4 py-2.5 rounded-xl bg-gradient-to-r from-blue-600 to-teal-600 text-white text-sm hover:from-blue-700 hover:to-teal-700 shadow-md shadow-blue-200 transition-all active:scale-95"
          >
            <Zap className="size-4" />
            ZENITH AI
          </button>
        </div>
      </div>

      {/* в”Ђв”Ђ Stats в”Ђв”Ђ */}
      <div className="grid grid-cols-2 lg:grid-cols-4 gap-4">
        {STATS.map(s => <StatCard key={s.label} stat={s} />)}
      </div>

      {/* в”Ђв”Ђ ZENITH AI quick bar в”Ђв”Ђ */}
      <div className="bg-gradient-to-r from-blue-600 via-blue-700 to-teal-600 rounded-2xl p-5 relative overflow-hidden">
        <div className="absolute -top-10 right-10 size-40 bg-white/5 rounded-full blur-2xl pointer-events-none" />
        <div className="relative z-10 flex flex-col sm:flex-row gap-4 items-center">
          <div className="flex items-center gap-3 flex-shrink-0">
            <div className="size-10 rounded-xl bg-white/15 flex items-center justify-center">
              <Bot className="size-5 text-white" />
            </div>
            <div>
              <p className="text-sm text-white">ZENITH AI</p>
              <p className="text-xs text-blue-200">Р’Р°С€РёСЏС‚ AI С„РёСЂРјРµРЅ РјРµРЅРёРґР¶СЉСЂ</p>
            </div>
          </div>
          <div className="flex-1 flex gap-2 w-full sm:w-auto">
            <input
              type="text"
              value={aiInput}
              onChange={e => setAiInput(e.target.value)}
              placeholder="РџРѕРїРёС‚Р°Р№ AI РёР»Рё РґР°Р№ РєРѕРјР°РЅРґР°... РЅР°РїСЂ. Р“РµРЅРµСЂРёСЂР°Р№ РљРЎРЎ Р·Р° Р±Р°РЅСЏ 8 РєРІ.Рј"
              className="flex-1 px-4 py-2.5 rounded-xl bg-white/15 border border-white/20 text-white placeholder-blue-200 text-sm focus:outline-none focus:bg-white/20 transition-all"
              onKeyDown={e => e.key === "Enter" && navigate("/pro/ai")}
            />
            <button
              onClick={() => navigate("/pro/ai")}
              className="px-4 py-2.5 rounded-xl bg-white text-blue-700 text-sm hover:bg-blue-50 transition-all flex items-center gap-1.5 flex-shrink-0"
            >
              <Send className="size-4" />
              <span className="hidden sm:inline">РР·РїСЂР°С‚Рё</span>
            </button>
          </div>
        </div>
        {/* Quick suggestions */}
        <div className="relative z-10 mt-3 flex flex-wrap gap-2">
          {[
            "РђРЅР°Р»РёР·РёСЂР°Р№ РїСЂРѕРµРєС‚ Р“РµСЂРјР°РЅ",
            "Р“РµРЅРµСЂРёСЂР°Р№ РґРѕРіРѕРІРѕСЂ Р·Р° РњР°СЂРёСЏ РРІР°РЅРѕРІР°",
            "Р¤РёРЅР°РЅСЃРѕРІ РѕС‚С‡РµС‚ Р·Р° РјР°СЂС‚",
            "Р Р°Р·РїСЂРµРґРµР»Рё Р·Р°РґР°С‡Рё РЅР° РµРєРёРїР°",
          ].map(s => (
            <button
              key={s}
              onClick={() => navigate("/pro/ai")}
              className="px-3 py-1 rounded-full bg-white/10 border border-white/15 text-xs text-white/80 hover:bg-white/20 transition-all"
            >
              {s}
            </button>
          ))}
        </div>
      </div>

      {/* в”Ђв”Ђ Quick actions + Notifications в”Ђв”Ђ */}
      <div className="grid grid-cols-1 lg:grid-cols-3 gap-5">
        {/* Quick actions */}
        <div className="lg:col-span-2 bg-white rounded-2xl border border-gray-100 p-5">
          <div className="flex items-center justify-between mb-4">
            <p className="text-sm text-gray-800">Р‘СЉСЂР·Рё РґРµР№СЃС‚РІРёСЏ</p>
            <Sparkles className="size-4 text-blue-400" />
          </div>
          <div className="grid grid-cols-2 gap-3">
            {AI_ACTIONS.map(a => {
              const Icon = a.icon;
              return (
                <Link
                  key={a.label}
                  to={a.to}
                  className="flex items-center gap-3 p-4 rounded-xl border border-gray-100 hover:border-blue-100 hover:shadow-sm transition-all group"
                >
                  <div className={`size-9 rounded-xl ${a.bg} flex items-center justify-center flex-shrink-0 group-hover:scale-110 transition-transform`}>
                    <Icon className={`size-4 ${a.color}`} />
                  </div>
                  <div className="min-w-0">
                    <p className="text-sm text-gray-800 truncate">{a.label}</p>
                    <p className="text-xs text-gray-400 truncate">{a.sub}</p>
                  </div>
                </Link>
              );
            })}
          </div>
        </div>

        {/* Notifications */}
        <div className="bg-white rounded-2xl border border-gray-100 p-5">
          <div className="flex items-center justify-between mb-4">
            <p className="text-sm text-gray-800">РР·РІРµСЃС‚РёСЏ</p>
            <span className="size-5 rounded-full bg-red-100 text-red-600 text-xs flex items-center justify-center">
              {NOTIFICATIONS.length}
            </span>
          </div>
          <div className="space-y-3">
            {NOTIFICATIONS.map((n, i) => {
              const Icon = n.icon;
              return (
                <div key={i} className="flex items-start gap-3">
                  <Icon className={`size-4 flex-shrink-0 mt-0.5 ${n.color}`} />
                  <p className="text-xs text-gray-600 flex-1 leading-relaxed">{n.text}</p>
                  <span className="text-[10px] text-gray-400 flex-shrink-0">{n.time}</span>
                </div>
              );
            })}
          </div>
        </div>
      </div>

      {/* в”Ђв”Ђ Projects table в”Ђв”Ђ */}
      <div className="bg-white rounded-2xl border border-gray-100">
        <div className="flex items-center justify-between px-5 py-4 border-b border-gray-50">
          <p className="text-sm text-gray-800">РђРєС‚РёРІРЅРё РїСЂРѕРµРєС‚Рё</p>
          <Link to="/pro/projects" className="flex items-center gap-1 text-xs text-blue-600 hover:text-blue-700 transition-colors">
            Р’СЃРёС‡РєРё <ArrowRight className="size-3" />
          </Link>
        </div>
        <div className="px-4 py-2">
          {PROJECTS.map(p => <ProjectRow key={p.id} proj={p} />)}
        </div>
      </div>

    </div>
  );
}


// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ
// FILE: src/app/pages/pro/ProAIPage.tsx
// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ

import { useState, useRef, useEffect } from "react";
import {
  Bot, Send, Sparkles, Zap, Calculator, FileText,
  BarChart3, Users, Mic, RefreshCw, Copy, ThumbsUp,
  Crown, Paperclip,
} from "lucide-react";

type Msg = { role: "user" | "ai"; text: string; time: string };

const SUGGESTIONS = [
  { icon: Calculator, text: "Р“РµРЅРµСЂРёСЂР°Р№ РљРЎРЎ Р·Р° Р±Р°РЅСЏ 8 РєРІ.Рј СЃ С‚РµСЂР°РєРѕС‚ Рё Р’РёРљ" },
  { icon: FileText,   text: "РР·РіРѕС‚РІРё РґРѕРіРѕРІРѕСЂ Р·Р° СЂРµРјРѕРЅС‚ СЃ РєР»РёРµРЅС‚ РРІР°РЅ РџРµС‚СЂРѕРІ" },
  { icon: BarChart3,  text: "Р¤РёРЅР°РЅСЃРѕРІ Р°РЅР°Р»РёР· Р·Р° РїСЂРѕРµРєС‚ Р’РёС‚РѕС€Р° 24 Р·Р° РјР°СЂС‚" },
  { icon: Users,      text: "Р Р°Р·РїСЂРµРґРµР»Рё Р·Р°РґР°С‡РёС‚Рµ РЅР° РµРєРёРїР° Р·Р° С‚Р°Р·Рё СЃРµРґРјРёС†Р°" },
];

const INITIAL_MSGS: Msg[] = [
  {
    role: "ai",
    text: "Р—РґСЂР°РІРµР№С‚Рµ! РђР· СЃСЉРј **ZENITH AI** вЂ” РІР°С€РёСЏС‚ PRO С„РёСЂРјРµРЅ Р°СЃРёСЃС‚РµРЅС‚. РњРѕРіР° РґР°:\n\nвЂў Р“РµРЅРµСЂРёСЂР°Рј РїСЉР»РЅРё РљРЎРЎ СЃ С„РѕСЂРјСѓР»Рё Рё РјР°С‚РµСЂРёР°Р»Рё\nвЂў РР·РіРѕС‚РІСЏРј РґРѕРіРѕРІРѕСЂРё Рё РѕС„РµСЂС‚Рё\nвЂў РђРЅР°Р»РёР·РёСЂР°Рј С„РёРЅР°РЅСЃРёС‚Рµ РЅР° РїСЂРѕРµРєС‚РёС‚Рµ\nвЂў РЈРїСЂР°РІР»СЏРІР°Рј Р·Р°РґР°С‡Рё РЅР° РµРєРёРїР°\nвЂў Р”Р°РІР°Рј Р±РёР·РЅРµСЃ СЃСЉРІРµС‚Рё Р·Р° СЃС‚СЂРѕРёС‚РµР»РЅРёСЏ СЃРµРєС‚РѕСЂ\n\nРЎ РєР°РєРІРѕ РґР° РІРё РїРѕРјРѕРіРЅР° РґРЅРµСЃ?",
    time: "СЃРµРіР°",
  },
];

const AI_RESPONSES: Record<string, string> = {
  default: "Р Р°Р·Р±РёСЂР°Рј РІР°С€Р°С‚Р° Р·Р°СЏРІРєР°. РђРЅР°Р»РёР·РёСЂР°Рј РґР°РЅРЅРёС‚Рµ РѕС‚ РІР°С€Р°С‚Р° С„РёСЂРјР°...\n\n**ZENITH AI** РѕР±СЂР°Р±РѕС‚РІР° Р·Р°РїРёС‚РІР°РЅРµС‚Рѕ Рё С‰Рµ РіРµРЅРµСЂРёСЂР° РґРµС‚Р°Р№Р»РµРЅ РѕС‚РіРѕРІРѕСЂ. Р’ РїСЉР»РЅР°С‚Р° РёРЅС‚РµРіСЂР°С†РёСЏ С‚РѕРІР° СЃРµ СЃРІСЉСЂР·РІР° СЃ РІР°С€РёС‚Рµ РїСЂРѕРµРєС‚РЅРё РґР°РЅРЅРё, С†РµРЅРѕРІРё Р»РёСЃС‚Рё Рё С„РёСЂРјРµРЅР° РёСЃС‚РѕСЂРёСЏ Р·Р° РјР°РєСЃРёРјР°Р»РЅРѕ С‚РѕС‡РµРЅ СЂРµР·СѓР»С‚Р°С‚.\n\n*РўРµСЃС‚РѕРІР° РґРµРјРѕ СЃСЂРµРґР° вЂ” СЂРµР°Р»РЅРёС‚Рµ РѕС‚РіРѕРІРѕСЂРё С‰Рµ СЃР° РїРµСЂСЃРѕРЅР°Р»РёР·РёСЂР°РЅРё Р·Р° РЎРљ РЎС‚СЂРѕР№ Р•РћРћР”.*",
  Рєss: "**РљРЎРЎ РіРµРЅРµСЂРёСЂР°РЅР° СѓСЃРїРµС€РЅРѕ!** рџЋ‰\n\n**Р‘Р°РЅСЏ 8 РєРІ.Рј вЂ” РљРѕР»РёС‡РµСЃС‚РІРµРЅРѕ-СЃС‚РѕР№РЅРѕСЃС‚РЅР° СЃРјРµС‚РєР°**\n\n| РџРѕР·РёС†РёСЏ | Р•Рґ. | РљРѕР». | Р•Рґ.С†РµРЅР° | РЎСѓРјР° |\n|---|---|---|---|---|\n| Р”РµРјРѕРЅС‚Р°Р¶ | РєРІ.Рј | 8 | 25 Р»РІ | 200 Р»РІ |\n| РҐРёРґСЂРѕРёР·РѕР»Р°С†РёСЏ | РєРІ.Рј | 10 | 45 Р»РІ | 450 Р»РІ |\n| РўРµСЂР°РєРѕС‚ РїРѕРґ | РєРІ.Рј | 8 | 85 Р»РІ | 680 Р»РІ |\n| РўРµСЂР°РєРѕС‚ СЃС‚РµРЅРё | РєРІ.Рј | 32 | 90 Р»РІ | 2 880 Р»РІ |\n| Р’РёРљ РјРѕРЅС‚Р°Р¶ | Р±СЂ | 1 | 800 Р»РІ | 800 Р»РІ |\n| **РћР‘Р©Рћ** | | | | **5 010 Р»РІ** |\n\nвњ… Р“РѕС‚РѕРІР° Р·Р° РёР·РїСЂР°С‰Р°РЅРµ РєР°С‚Рѕ PDF РѕС„РµСЂС‚Р°",
  РґРѕРіРѕРІРѕСЂ: "**Р”РѕРіРѕРІРѕСЂ Р·Р° СЃС‚СЂРѕРёС‚РµР»РЅРѕ-СЂРµРјРѕРЅС‚РЅРё РґРµР№РЅРѕСЃС‚Рё**\n\nРЎСЉСЃС‚Р°РІРµРЅ СЃСЉРј С‡РµСЂРЅРѕРІР° РґРѕРіРѕРІРѕСЂ РјРµР¶РґСѓ:\nвЂў **РР·РїСЉР»РЅРёС‚РµР»:** РЎРљ РЎС‚СЂРѕР№ Р•РћРћР”\nвЂў **РљР»РёРµРЅС‚:** [РџРѕСЃРѕС‡РµС‚Рµ РєР»РёРµРЅС‚]\n\n**РћСЃРЅРѕРІРЅРё РєР»Р°СѓР·Рё:**\n1. РЎСЂРѕРє РЅР° РёР·РїСЉР»РЅРµРЅРёРµ: __ РґРЅРё РѕС‚ РїРѕРґРїРёСЃРІР°РЅРµС‚Рѕ\n2. РћР±С‰Р° СЃС‚РѕР№РЅРѕСЃС‚: __ Р»РІ Р±РµР· Р”Р”РЎ\n3. РђРІР°РЅСЃРѕРІРѕ РїР»Р°С‰Р°РЅРµ: 30% РїСЂРё РїРѕРґРїРёСЃРІР°РЅРµ\n4. Р“Р°СЂР°РЅС†РёРѕРЅРµРЅ СЃСЂРѕРє: 24 РјРµСЃРµС†Р°\n5. РќРµСѓСЃС‚РѕР№РєР°: 0.1% Р·Р° РІСЃРµРєРё РґРµРЅ Р·Р°РєСЉСЃРЅРµРЅРёРµ\n\n*Р”РѕРєСѓРјРµРЅС‚СЉС‚ С‰Рµ Р±СЉРґРµ РіРѕС‚РѕРІ Р·Р° РїРѕРґРїРёСЃ СЃР»РµРґ РїРѕРїСЉР»РІР°РЅРµ РЅР° РґР°РЅРЅРёС‚Рµ.*",
};

function getAIResponse(text: string): string {
  const lower = text.toLowerCase();
  if (lower.includes("Рєss") || lower.includes("РєСЃ") || lower.includes("СЃРјРµС‚РєР°") || lower.includes("Р±Р°РЅСЏ")) return AI_RESPONSES.Рєss;
  if (lower.includes("РґРѕРіРѕРІРѕСЂ") || lower.includes("РѕС„РµСЂС‚Р°")) return AI_RESPONSES.РґРѕРіРѕРІРѕСЂ;
  return AI_RESPONSES.default;
}

function formatTime() {
  return new Date().toLocaleTimeString("bg-BG", { hour: "2-digit", minute: "2-digit" });
}

// Minimal markdown renderer
function MsgText({ text }: { text: string }) {
  const parts = text.split(/(\*\*[^*]+\*\*|\n)/g);
  return (
    <p className="text-sm leading-relaxed whitespace-pre-wrap">
      {parts.map((p, i) => {
        if (p.startsWith("**") && p.endsWith("**")) {
          return <strong key={i} className="font-semibold">{p.slice(2, -2)}</strong>;
        }
        if (p === "\n") return <br key={i} />;
        return <span key={i}>{p}</span>;
      })}
    </p>
  );
}

export function ProAIPage() {
  const [msgs, setMsgs] = useState<Msg[]>(INITIAL_MSGS);
  const [input, setInput] = useState("");
  const [loading, setLoading] = useState(false);
  const bottomRef = useRef<HTMLDivElement>(null);

  useEffect(() => {
    bottomRef.current?.scrollIntoView({ behavior: "smooth" });
  }, [msgs]);

  const send = (text = input.trim()) => {
    if (!text || loading) return;
    const userMsg: Msg = { role: "user", text, time: formatTime() };
    setMsgs(prev => [...prev, userMsg]);
    setInput("");
    setLoading(true);
    setTimeout(() => {
      const aiMsg: Msg = { role: "ai", text: getAIResponse(text), time: formatTime() };
      setMsgs(prev => [...prev, aiMsg]);
      setLoading(false);
    }, 1200);
  };

  return (
    <div className="flex flex-col h-full">
      {/* Header */}
      <div className="px-5 py-4 border-b border-gray-100 bg-white flex items-center gap-3 flex-shrink-0">
        <div className="size-9 rounded-xl bg-gradient-to-br from-blue-600 to-teal-500 flex items-center justify-center shadow-sm">
          <Bot className="size-5 text-white" />
        </div>
        <div>
          <div className="flex items-center gap-2">
            <p className="text-sm text-gray-800">ZENITH AI</p>
            <span className="px-1.5 py-0.5 rounded-full bg-gradient-to-r from-blue-600 to-teal-500 text-white text-[9px]">PRO</span>
          </div>
          <p className="text-xs text-gray-400">AI С„РёСЂРјРµРЅ РјРµРЅРёРґР¶СЉСЂ В· РћРЅР»Р°Р№РЅ</p>
        </div>
        <div className="ml-auto flex items-center gap-2">
          <button className="size-8 flex items-center justify-center rounded-lg text-gray-400 hover:bg-gray-100 transition-colors" title="РќРѕРІ С‡Р°С‚" onClick={() => setMsgs(INITIAL_MSGS)}>
            <RefreshCw className="size-4" />
          </button>
          <div className="flex items-center gap-1.5 px-2 py-1 rounded-full bg-emerald-50 border border-emerald-100">
            <span className="size-1.5 rounded-full bg-emerald-500 animate-pulse" />
            <span className="text-xs text-emerald-600">РђРєС‚РёРІРµРЅ</span>
          </div>
        </div>
      </div>

      {/* Messages */}
      <div className="flex-1 overflow-y-auto px-5 py-4 space-y-4">
        {/* Suggestions (first load) */}
        {msgs.length === 1 && (
          <div className="grid grid-cols-1 sm:grid-cols-2 gap-2 mb-4">
            {SUGGESTIONS.map(s => {
              const Icon = s.icon;
              return (
                <button
                  key={s.text}
                  onClick={() => send(s.text)}
                  className="flex items-center gap-3 p-3.5 rounded-xl border border-gray-100 hover:border-blue-200 hover:bg-blue-50/50 text-left transition-all group"
                >
                  <Icon className="size-4 text-blue-500 flex-shrink-0 group-hover:scale-110 transition-transform" />
                  <span className="text-xs text-gray-600">{s.text}</span>
                </button>
              );
            })}
          </div>
        )}

        {msgs.map((m, i) => (
          <div key={i} className={`flex gap-3 ${m.role === "user" ? "flex-row-reverse" : ""}`}>
            {m.role === "ai" ? (
              <div className="size-8 rounded-xl bg-gradient-to-br from-blue-600 to-teal-500 flex items-center justify-center flex-shrink-0 shadow-sm mt-1">
                <Sparkles className="size-4 text-white" />
              </div>
            ) : (
              <div className="size-8 rounded-full bg-gradient-to-br from-violet-500 to-blue-600 flex items-center justify-center text-white text-xs flex-shrink-0 mt-1">
                РЎРЎ
              </div>
            )}
            <div className={`max-w-[80%] ${m.role === "user" ? "items-end" : "items-start"} flex flex-col gap-1`}>
              <div
                className={`px-4 py-3 rounded-2xl ${
                  m.role === "user"
                    ? "bg-gradient-to-br from-blue-600 to-teal-600 text-white rounded-tr-md"
                    : "bg-white border border-gray-100 text-gray-800 rounded-tl-md shadow-sm"
                }`}
              >
                {m.role === "ai" ? <MsgText text={m.text} /> : <p className="text-sm leading-relaxed">{m.text}</p>}
              </div>
              <div className={`flex items-center gap-2 ${m.role === "user" ? "flex-row-reverse" : ""}`}>
                <span className="text-[10px] text-gray-400">{m.time}</span>
                {m.role === "ai" && (
                  <>
                    <button className="text-gray-300 hover:text-gray-500 transition-colors"><Copy className="size-3" /></button>
                    <button className="text-gray-300 hover:text-emerald-500 transition-colors"><ThumbsUp className="size-3" /></button>
                  </>
                )}
              </div>
            </div>
          </div>
        ))}

        {loading && (
          <div className="flex gap-3">
            <div className="size-8 rounded-xl bg-gradient-to-br from-blue-600 to-teal-500 flex items-center justify-center flex-shrink-0 shadow-sm">
              <Sparkles className="size-4 text-white" />
            </div>
            <div className="bg-white border border-gray-100 rounded-2xl rounded-tl-md px-4 py-3 shadow-sm">
              <div className="flex gap-1 items-center h-5">
                <span className="size-2 rounded-full bg-blue-400 animate-bounce" style={{ animationDelay: "0ms" }} />
                <span className="size-2 rounded-full bg-blue-400 animate-bounce" style={{ animationDelay: "150ms" }} />
                <span className="size-2 rounded-full bg-teal-400 animate-bounce" style={{ animationDelay: "300ms" }} />
              </div>
            </div>
          </div>
        )}
        <div ref={bottomRef} />
      </div>

      {/* Input */}
      <div className="px-4 py-4 border-t border-gray-100 bg-white flex-shrink-0">
        <div className="flex gap-2 items-end">
          <button className="size-9 flex items-center justify-center rounded-xl border border-gray-200 text-gray-400 hover:bg-gray-50 transition-colors flex-shrink-0">
            <Paperclip className="size-4" />
          </button>
          <div className="flex-1 relative">
            <textarea
              rows={1}
              value={input}
              onChange={e => setInput(e.target.value)}
              onKeyDown={e => { if (e.key === "Enter" && !e.shiftKey) { e.preventDefault(); send(); } }}
              placeholder="РќР°РїРёС€РµС‚Рµ РєРѕРјР°РЅРґР° РёР»Рё РІСЉРїСЂРѕСЃвЂ¦ (Enter Р·Р° РёР·РїСЂР°С‰Р°РЅРµ)"
              className="w-full px-4 py-2.5 rounded-xl border border-gray-200 text-sm text-gray-700 placeholder-gray-400 focus:outline-none focus:ring-2 focus:ring-blue-500/20 focus:border-blue-400 transition-all resize-none"
            />
          </div>
          <button className="size-9 flex items-center justify-center rounded-xl border border-gray-200 text-gray-400 hover:bg-gray-50 transition-colors flex-shrink-0">
            <Mic className="size-4" />
          </button>
          <button
            onClick={() => send()}
            disabled={!input.trim() || loading}
            className="size-9 flex items-center justify-center rounded-xl bg-gradient-to-br from-blue-600 to-teal-600 text-white hover:from-blue-700 hover:to-teal-700 disabled:opacity-40 transition-all flex-shrink-0 shadow-md shadow-blue-200 active:scale-95"
          >
            <Send className="size-4" />
          </button>
        </div>
        <p className="text-center text-[10px] text-gray-400 mt-2">
          ZENITH AI РјРѕР¶Рµ РґР° РїСЂР°РІРё РіСЂРµС€РєРё В· РџСЂРѕРІРµСЂСЏРІР°Р№С‚Рµ РІР°Р¶РЅР° РёРЅС„РѕСЂРјР°С†РёСЏ
        </p>
      </div>
    </div>
  );
}



// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ
// FILE: src/app/pages/pro/ProKSSPage.tsx
// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ

import { useState } from "react";
import {
  Calculator, Plus, Trash2, Download, Send, Sparkles,
  ChevronDown, Eye, FileText, RefreshCw,
} from "lucide-react";

type Row = { id: number; name: string; unit: string; qty: string; price: string };

const UNITS = ["РєРІ.Рј", "Р».Рј", "Р±СЂ", "Рє.Рі", "РєСѓР±.Рј", "С‡.С‚СЂСѓРґ", "РєРѕРјРїР»."];

const TEMPLATES = [
  { label: "Р‘Р°РЅСЏ вЂ” РїСЉР»РµРЅ СЂРµРјРѕРЅС‚",    rows: [
    { id: 1, name: "Р”РµРјРѕРЅС‚Р°Р¶ РїР»РѕС‡РєРё", unit: "РєРІ.Рј", qty: "24", price: "25" },
    { id: 2, name: "РҐРёРґСЂРѕРёР·РѕР»Р°С†РёСЏ",   unit: "РєРІ.Рј", qty: "30", price: "45" },
    { id: 3, name: "РўРµСЂР°РєРѕС‚ РїРѕРґ",      unit: "РєРІ.Рј", qty: "8",  price: "85" },
    { id: 4, name: "РўРµСЂР°РєРѕС‚ СЃС‚РµРЅРё",   unit: "РєРІ.Рј", qty: "32", price: "90" },
    { id: 5, name: "Р’РёРљ РјРѕРЅС‚Р°Р¶",      unit: "РєРѕРјРїР».", qty: "1", price: "950" },
    { id: 6, name: "Р‘РѕСЏРґР¶РёР№СЃРєРё С‚СЂСѓРґ", unit: "РєРІ.Рј", qty: "30", price: "18" },
  ]},
  { label: "Р‘РѕСЏРґРёСЃРІР°РЅРµ Р°РїР°СЂС‚Р°РјРµРЅС‚", rows: [
    { id: 1, name: "Р“СЂСѓРЅРґРёСЂР°РЅРµ",      unit: "РєРІ.Рј", qty: "120", price: "6"  },
    { id: 2, name: "РЁРїР°РєР»РѕРІР°РЅРµ",      unit: "РєРІ.Рј", qty: "120", price: "12" },
    { id: 3, name: "Р‘РѕСЏРґРёСЃРІР°РЅРµ 2 РїР».", unit: "РєРІ.Рј", qty: "120", price: "14" },
    { id: 4, name: "РўР°РїРµС‚Рё/РµС„РµРєС‚",    unit: "РєРІ.Рј", qty: "40",  price: "35" },
  ]},
  { label: "РџРѕРґРѕРІР° РЅР°СЃС‚РёР»РєР°",        rows: [
    { id: 1, name: "Р”РµРјРѕРЅС‚Р°Р¶ СЃС‚Р°СЂР° РЅР°СЃС‚РёР»РєР°", unit: "РєРІ.Рј", qty: "50", price: "15" },
    { id: 2, name: "РР·СЂР°РІРЅРёС‚РµР»РЅР° Р·Р°РјР°Р·РєР°",    unit: "РєРІ.Рј", qty: "50", price: "30" },
    { id: 3, name: "Р›Р°РјРёРЅР°С‚/РїР°СЂРєРµС‚",          unit: "РєРІ.Рј", qty: "50", price: "45" },
    { id: 4, name: "РџРµСЂРІР°Р·Рё",                 unit: "Р».Рј",  qty: "30", price: "12" },
  ]},
];

let nextId = 10;

export function ProKSSPage() {
  const [title, setTitle] = useState("РќРѕРІР° РљРЎРЎ");
  const [client, setClient] = useState("");
  const [rows, setRows] = useState<Row[]>([
    { id: 1, name: "", unit: "РєРІ.Рј", qty: "", price: "" },
  ]);
  const [vat, setVat] = useState(true);
  const [showTemplate, setShowTemplate] = useState(false);
  const [generated, setGenerated] = useState(false);

  const addRow = () => {
    setRows(prev => [...prev, { id: nextId++, name: "", unit: "РєРІ.Рј", qty: "", price: "" }]);
  };

  const removeRow = (id: number) => {
    setRows(prev => prev.filter(r => r.id !== id));
  };

  const update = (id: number, field: keyof Row, val: string) => {
    setRows(prev => prev.map(r => r.id === id ? { ...r, [field]: val } : r));
  };

  const subtotal = rows.reduce((acc, r) => {
    const q = parseFloat(r.qty) || 0;
    const p = parseFloat(r.price) || 0;
    return acc + q * p;
  }, 0);
  const vatAmt = vat ? subtotal * 0.2 : 0;
  const total = subtotal + vatAmt;

  const loadTemplate = (t: typeof TEMPLATES[0]) => {
    setRows(t.rows.map(r => ({ ...r })));
    setTitle(t.label);
    setShowTemplate(false);
  };

  return (
    <div className="p-5 lg:p-7 max-w-5xl mx-auto space-y-6">
      {/* Header */}
      <div className="flex flex-col sm:flex-row sm:items-center justify-between gap-3">
        <div>
          <h1 className="text-xl text-gray-800">РљРЎРЎ Р“РµРЅРµСЂР°С‚РѕСЂ</h1>
          <p className="text-sm text-gray-500 mt-0.5">РљРѕР»РёС‡РµСЃС‚РІРµРЅРѕ-СЃС‚РѕР№РЅРѕСЃС‚РЅР° СЃРјРµС‚РєР° СЃ AI</p>
        </div>
        <div className="flex gap-2">
          <div className="relative">
            <button
              onClick={() => setShowTemplate(!showTemplate)}
              className="flex items-center gap-1.5 px-3 py-2 rounded-xl border border-gray-200 text-gray-700 text-sm hover:bg-gray-50 transition-all"
            >
              <Sparkles className="size-4 text-blue-500" />
              AI РЁР°Р±Р»РѕРЅ
              <ChevronDown className="size-3.5" />
            </button>
            {showTemplate && (
              <div className="absolute right-0 top-full mt-1 bg-white border border-gray-100 rounded-xl shadow-lg z-10 min-w-[200px] overflow-hidden">
                {TEMPLATES.map(t => (
                  <button
                    key={t.label}
                    onClick={() => loadTemplate(t)}
                    className="w-full text-left px-4 py-2.5 text-sm text-gray-700 hover:bg-blue-50 hover:text-blue-700 transition-colors"
                  >
                    {t.label}
                  </button>
                ))}
              </div>
            )}
          </div>
          <button
            onClick={() => setGenerated(true)}
            className="flex items-center gap-1.5 px-4 py-2 rounded-xl bg-gradient-to-r from-blue-600 to-teal-600 text-white text-sm hover:from-blue-700 hover:to-teal-700 shadow-md shadow-blue-200 transition-all active:scale-95"
          >
            <Eye className="size-4" />
            РџСЂРµРіР»РµРґ PDF
          </button>
        </div>
      </div>

      {/* Meta */}
      <div className="bg-white rounded-2xl border border-gray-100 p-5 grid grid-cols-1 sm:grid-cols-2 gap-4">
        <div>
          <label className="text-xs text-gray-500 mb-1 block">Р—Р°РіР»Р°РІРёРµ РЅР° РљРЎРЎ</label>
          <input
            value={title}
            onChange={e => setTitle(e.target.value)}
            className="w-full px-3 py-2 rounded-xl border border-gray-200 text-sm text-gray-800 focus:outline-none focus:ring-2 focus:ring-blue-500/20 focus:border-blue-400 transition-all"
          />
        </div>
        <div>
          <label className="text-xs text-gray-500 mb-1 block">РљР»РёРµРЅС‚</label>
          <input
            value={client}
            onChange={e => setClient(e.target.value)}
            placeholder="РРІР°РЅ РџРµС‚СЂРѕРІ / Р¤РёСЂРјР° РћРћР”"
            className="w-full px-3 py-2 rounded-xl border border-gray-200 text-sm text-gray-800 placeholder-gray-400 focus:outline-none focus:ring-2 focus:ring-blue-500/20 focus:border-blue-400 transition-all"
          />
        </div>
      </div>

      {/* Table */}
      <div className="bg-white rounded-2xl border border-gray-100 overflow-hidden">
        <div className="overflow-x-auto">
          <table className="w-full min-w-[600px]">
            <thead>
              <tr className="border-b border-gray-100 bg-gray-50/70">
                <th className="text-left px-4 py-3 text-xs text-gray-400 w-8">#</th>
                <th className="text-left px-4 py-3 text-xs text-gray-400">РћРїРёСЃР°РЅРёРµ РЅР° РґРµР№РЅРѕСЃС‚С‚Р°</th>
                <th className="text-left px-4 py-3 text-xs text-gray-400 w-28">Р•Рґ.РјСЏСЂРєР°</th>
                <th className="text-right px-4 py-3 text-xs text-gray-400 w-24">РљРѕР»РёС‡РµСЃС‚РІРѕ</th>
                <th className="text-right px-4 py-3 text-xs text-gray-400 w-28">Р•Рґ.С†РµРЅР° (Р»РІ)</th>
                <th className="text-right px-4 py-3 text-xs text-gray-400 w-28">РЎСѓРјР° (Р»РІ)</th>
                <th className="w-10" />
              </tr>
            </thead>
            <tbody>
              {rows.map((row, idx) => {
                const sum = (parseFloat(row.qty) || 0) * (parseFloat(row.price) || 0);
                return (
                  <tr key={row.id} className="border-b border-gray-50 last:border-0 hover:bg-gray-50/50 transition-colors">
                    <td className="px-4 py-2.5 text-xs text-gray-400">{idx + 1}</td>
                    <td className="px-4 py-2">
                      <input
                        value={row.name}
                        onChange={e => update(row.id, "name", e.target.value)}
                        placeholder="РћРїРёСЃР°РЅРёРµ РЅР° РґРµР№РЅРѕСЃС‚С‚Р°вЂ¦"
                        className="w-full text-sm text-gray-700 placeholder-gray-300 focus:outline-none bg-transparent"
                      />
                    </td>
                    <td className="px-4 py-2">
                      <select
                        value={row.unit}
                        onChange={e => update(row.id, "unit", e.target.value)}
                        className="text-sm text-gray-700 focus:outline-none bg-transparent cursor-pointer w-full"
                      >
                        {UNITS.map(u => <option key={u}>{u}</option>)}
                      </select>
                    </td>
                    <td className="px-4 py-2">
                      <input
                        type="number"
                        value={row.qty}
                        onChange={e => update(row.id, "qty", e.target.value)}
                        placeholder="0"
                        className="w-full text-sm text-gray-700 text-right placeholder-gray-300 focus:outline-none bg-transparent"
                      />
                    </td>
                    <td className="px-4 py-2">
                      <input
                        type="number"
                        value={row.price}
                        onChange={e => update(row.id, "price", e.target.value)}
                        placeholder="0.00"
                        className="w-full text-sm text-gray-700 text-right placeholder-gray-300 focus:outline-none bg-transparent"
                      />
                    </td>
                    <td className="px-4 py-2.5 text-sm text-gray-800 text-right">
                      {sum > 0 ? `${sum.toFixed(2)}` : "вЂ”"}
                    </td>
                    <td className="px-2">
                      <button
                        onClick={() => removeRow(row.id)}
                        disabled={rows.length === 1}
                        className="size-7 flex items-center justify-center rounded-lg text-gray-300 hover:text-red-400 hover:bg-red-50 disabled:opacity-0 transition-all"
                      >
                        <Trash2 className="size-3.5" />
                      </button>
                    </td>
                  </tr>
                );
              })}
            </tbody>
          </table>
        </div>

        <div className="px-4 py-3 border-t border-gray-50">
          <button
            onClick={addRow}
            className="flex items-center gap-2 text-sm text-blue-600 hover:text-blue-700 transition-colors"
          >
            <Plus className="size-4" />
            Р”РѕР±Р°РІРё СЂРµРґ
          </button>
        </div>
      </div>

      {/* Totals */}
      <div className="flex flex-col sm:flex-row gap-4 items-start justify-between">
        <label className="flex items-center gap-2 cursor-pointer">
          <input
            type="checkbox"
            checked={vat}
            onChange={e => setVat(e.target.checked)}
            className="size-4 rounded accent-blue-600"
          />
          <span className="text-sm text-gray-600">Р”РѕР±Р°РІРё Р”Р”РЎ (20%)</span>
        </label>

        <div className="bg-white rounded-2xl border border-gray-100 p-5 w-full sm:w-72 space-y-2">
          <div className="flex justify-between text-sm">
            <span className="text-gray-500">РќРµС‚Рѕ СЃСѓРјР°</span>
            <span className="text-gray-800">{subtotal.toFixed(2)} Р»РІ</span>
          </div>
          {vat && (
            <div className="flex justify-between text-sm">
              <span className="text-gray-500">Р”Р”РЎ 20%</span>
              <span className="text-gray-800">{vatAmt.toFixed(2)} Р»РІ</span>
            </div>
          )}
          <div className="flex justify-between pt-2 border-t border-gray-100">
            <span className="text-gray-800">РћР‘Р©Рћ</span>
            <span className="text-blue-700 text-lg">{total.toFixed(2)} Р»РІ</span>
          </div>
        </div>
      </div>

      {/* Actions */}
      <div className="flex flex-wrap gap-3">
        <button className="flex items-center gap-2 px-4 py-2.5 rounded-xl border border-gray-200 text-gray-700 text-sm hover:bg-gray-50 transition-all">
          <RefreshCw className="size-4" />
          AI РґРѕРїСЉР»РІР°РЅРµ
        </button>
        <button className="flex items-center gap-2 px-4 py-2.5 rounded-xl border border-gray-200 text-gray-700 text-sm hover:bg-gray-50 transition-all">
          <Download className="size-4" />
          РР·С‚РµРіР»Рё PDF
        </button>
        <button className="flex items-center gap-2 px-4 py-2.5 rounded-xl border border-gray-200 text-gray-700 text-sm hover:bg-gray-50 transition-all">
          <FileText className="size-4" />
          Р—Р°РїР°Р·Рё
        </button>
        <button className="flex items-center gap-2 px-5 py-2.5 rounded-xl bg-gradient-to-r from-blue-600 to-teal-600 text-white text-sm hover:from-blue-700 hover:to-teal-700 shadow-md shadow-blue-200 transition-all active:scale-95 ml-auto">
          <Send className="size-4" />
          РР·РїСЂР°С‚Рё РЅР° РєР»РёРµРЅС‚Р°
        </button>
      </div>

      {/* Generated preview toast */}
      {generated && (
        <div className="fixed bottom-24 left-1/2 -translate-x-1/2 z-50 bg-gray-900 text-white px-5 py-3 rounded-xl shadow-2xl flex items-center gap-3 text-sm">
          <FileText className="size-4 text-teal-400" />
          PDF РїСЂРµРіР»РµРґ С‰Рµ Рµ РЅР°Р»РёС‡РµРЅ РІ РїСЉР»РЅР°С‚Р° РІРµСЂСЃРёСЏ
          <button onClick={() => setGenerated(false)} className="ml-2 text-gray-400 hover:text-white">вњ•</button>
        </div>
      )}
    </div>
  );
}



// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ
// FILE: src/app/pages/pro/ProProjectsPage.tsx
// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ

import { useState } from "react";
import {
  Search, Plus, Filter, Clock, CheckCircle2, AlertCircle,
  ChevronRight, MoreHorizontal, Calendar, Users, Euro,
} from "lucide-react";

const ALL_PROJECTS = [
  { id: 1, name: "Р РµРјРѕРЅС‚ Р°РїР°СЂС‚Р°РјРµРЅС‚ вЂ” СѓР». Р’РёС‚РѕС€Р° 24", client: "РњР°СЂРёСЏ РРІР°РЅРѕРІР°", value: "12 400 Р»РІ", progress: 72, status: "active", eta: "18 Р°РїСЂ", team: ["Р“РЎ", "РџР”"], type: "Р РµРјРѕРЅС‚" },
  { id: 2, name: "РЎС‚СЂРѕРµР¶ РІРёР»Р° вЂ” СЃ. Р“РµСЂРјР°РЅ", client: "РџРµС‚СЂРѕРІ & РЎРёРЅРѕРІРµ", value: "87 200 Р»РІ", progress: 34, status: "active", eta: "30 СЋРЅРё", team: ["РњРљ", "РЎРў", "РР’"], type: "РќРѕРІРѕ СЃС‚СЂРѕРёС‚РµР»СЃС‚РІРѕ" },
  { id: 3, name: "РћС„РёСЃ СЂРµРјРѕРЅС‚ вЂ” Р±СѓР». РҐСЂ. Р‘РѕС‚РµРІ", client: "Tech Soft OOD", value: "24 900 Р»РІ", progress: 90, status: "finishing", eta: "10 Р°РїСЂ", team: ["Р“РЎ"], type: "Р РµРјРѕРЅС‚" },
  { id: 4, name: "Р‘РѕСЏРґРёСЃРІР°РЅРµ Р¶РёР»РёС‰РµРЅ Р±Р»РѕРє", client: "Р•РЎ РР·С‚РѕРє", value: "8 700 Р»РІ", progress: 10, status: "pending", eta: "РњР°Р№", team: ["РџР”", "РњРљ"], type: "Р‘РѕСЏРґРёСЃРІР°РЅРµ" },
  { id: 5, name: "РўРµСЂР°РєРѕС‚ РєСѓС…РЅСЏ вЂ” СѓР». РћРїСЉР»С‡РµРЅСЃРєР° 44", client: "РЎРЅРµР¶Р°РЅР° Р“РµРѕСЂРіРёРµРІР°", value: "3 200 Р»РІ", progress: 0, status: "pending", eta: "15 Р°РїСЂ", team: ["РР’"], type: "Р”РѕРІСЉСЂС€РёС‚РµР»РЅРё" },
  { id: 6, name: "РР·РіСЂР°Р¶РґР°РЅРµ РіР°СЂР°Р¶ вЂ” РєРІ. Р›РѕР·РµРЅРµС†", client: "РҐСЂРёСЃС‚Рѕ РЎС‚РѕРµРІ", value: "18 600 Р»РІ", progress: 55, status: "active", eta: "28 Р°РїСЂ", team: ["РЎРў", "РњРљ"], type: "РќРѕРІРѕ СЃС‚СЂРѕРёС‚РµР»СЃС‚РІРѕ" },
  { id: 7, name: "РЎР°РЅРёСЂР°РЅРµ С„Р°СЃР°РґР°", client: "РЎРґСЂСѓР¶РµРЅРёРµ Р РѕР·Р°", value: "42 000 Р»РІ", progress: 100, status: "done", eta: "вЂ”", team: ["Р“РЎ", "РџР”", "РР’"], type: "РЎР°РЅРёСЂР°РЅРµ" },
  { id: 8, name: "РџРѕРєСЂРёРІ СЂРµРјРѕРЅС‚ вЂ” РІРёР»Р° Р‘РѕСЏРЅР°", client: "РљРѕРЅСЃС‚Р°РЅС‚РёРЅ Р›Р°Р·Р°СЂРѕРІ", value: "11 300 Р»РІ", progress: 100, status: "done", eta: "вЂ”", team: ["РњРљ"], type: "Р РµРјРѕРЅС‚" },
];

const STATUS_CFG: Record<string, { label: string; color: string; bg: string; icon: typeof Clock }> = {
  active:    { label: "РђРєС‚РёРІРµРЅ",    color: "text-blue-700",    bg: "bg-blue-50",    icon: Clock },
  finishing: { label: "Р¤РёРЅР°Р»РёР·РёСЂР°", color: "text-emerald-700", bg: "bg-emerald-50", icon: CheckCircle2 },
  pending:   { label: "РџСЂРµРґСЃС‚РѕРё",   color: "text-amber-700",   bg: "bg-amber-50",   icon: AlertCircle },
  done:      { label: "Р—Р°РІСЉСЂС€РµРЅ",   color: "text-gray-600",    bg: "bg-gray-100",   icon: CheckCircle2 },
};

export function ProProjectsPage() {
  const [q, setQ] = useState("");
  const [filter, setFilter] = useState<string>("all");

  const shown = ALL_PROJECTS.filter(p => {
    const matchQ = p.name.toLowerCase().includes(q.toLowerCase()) || p.client.toLowerCase().includes(q.toLowerCase());
    const matchF = filter === "all" || p.status === filter;
    return matchQ && matchF;
  });

  const counts = {
    all: ALL_PROJECTS.length,
    active: ALL_PROJECTS.filter(p => p.status === "active").length,
    finishing: ALL_PROJECTS.filter(p => p.status === "finishing").length,
    pending: ALL_PROJECTS.filter(p => p.status === "pending").length,
    done: ALL_PROJECTS.filter(p => p.status === "done").length,
  };

  return (
    <div className="p-5 lg:p-7 space-y-5">
      {/* Header */}
      <div className="flex flex-col sm:flex-row sm:items-center justify-between gap-3">
        <div>
          <h1 className="text-xl text-gray-800">РџСЂРѕРµРєС‚Рё</h1>
          <p className="text-sm text-gray-500 mt-0.5">{ALL_PROJECTS.length} РїСЂРѕРµРєС‚Р° РѕР±С‰Рѕ</p>
        </div>
        <button className="flex items-center gap-2 px-4 py-2.5 rounded-xl bg-gradient-to-r from-blue-600 to-teal-600 text-white text-sm hover:from-blue-700 hover:to-teal-700 shadow-md shadow-blue-200 transition-all active:scale-95 self-start sm:self-auto">
          <Plus className="size-4" />
          РќРѕРІ РїСЂРѕРµРєС‚
        </button>
      </div>

      {/* Filters */}
      <div className="flex flex-wrap gap-2">
        {(["all","active","finishing","pending","done"] as const).map(f => (
          <button
            key={f}
            onClick={() => setFilter(f)}
            className={`px-3 py-1.5 rounded-full text-xs transition-all ${
              filter === f
                ? "bg-blue-600 text-white shadow-sm"
                : "bg-white border border-gray-200 text-gray-600 hover:bg-gray-50"
            }`}
          >
            {{ all: "Р’СЃРёС‡РєРё", active: "РђРєС‚РёРІРЅРё", finishing: "Р¤РёРЅР°Р»РёР·РёСЂР°", pending: "РџСЂРµРґСЃС‚РѕРё", done: "Р—Р°РІСЉСЂС€РµРЅРё" }[f]}
            <span className={`ml-1.5 px-1.5 py-0.5 rounded-full text-[10px] ${filter === f ? "bg-white/20" : "bg-gray-100"}`}>
              {counts[f]}
            </span>
          </button>
        ))}
        <div className="flex-1" />
        <div className="relative">
          <Search className="absolute left-3 top-1/2 -translate-y-1/2 size-3.5 text-gray-400 pointer-events-none" />
          <input
            value={q}
            onChange={e => setQ(e.target.value)}
            placeholder="РўСЉСЂСЃРё РїСЂРѕРµРєС‚вЂ¦"
            className="pl-8 pr-3 py-1.5 text-xs border border-gray-200 rounded-xl focus:outline-none focus:ring-2 focus:ring-blue-500/20 focus:border-blue-400 transition-all bg-white w-48"
          />
        </div>
      </div>

      {/* Cards grid */}
      <div className="grid grid-cols-1 md:grid-cols-2 xl:grid-cols-3 gap-4">
        {shown.map(proj => {
          const s = STATUS_CFG[proj.status];
          const SIcon = s.icon;
          return (
            <div key={proj.id} className="bg-white rounded-2xl border border-gray-100 p-5 hover:shadow-md transition-all cursor-pointer group">
              <div className="flex items-start justify-between gap-2 mb-3">
                <div className="flex-1 min-w-0">
                  <p className="text-sm text-gray-800 leading-tight">{proj.name}</p>
                  <p className="text-xs text-gray-400 mt-0.5">{proj.client}</p>
                </div>
                <button className="size-7 flex items-center justify-center rounded-lg text-gray-300 hover:bg-gray-100 hover:text-gray-600 transition-all">
                  <MoreHorizontal className="size-4" />
                </button>
              </div>

              {/* Progress */}
              {proj.status !== "done" && (
                <div className="mb-3">
                  <div className="flex justify-between items-center mb-1">
                    <span className="text-xs text-gray-400">РџСЂРѕРіСЂРµСЃ</span>
                    <span className="text-xs text-gray-600">{proj.progress}%</span>
                  </div>
                  <div className="h-1.5 bg-gray-100 rounded-full overflow-hidden">
                    <div
                      className="h-full rounded-full bg-gradient-to-r from-blue-500 to-teal-500 transition-all"
                      style={{ width: `${proj.progress}%` }}
                    />
                  </div>
                </div>
              )}

              {/* Meta */}
              <div className="grid grid-cols-3 gap-2 mb-3">
                <div className="flex items-center gap-1.5">
                  <Euro className="size-3 text-gray-400" />
                  <span className="text-xs text-gray-600 truncate">{proj.value}</span>
                </div>
                <div className="flex items-center gap-1.5">
                  <Calendar className="size-3 text-gray-400" />
                  <span className="text-xs text-gray-600">{proj.eta}</span>
                </div>
                <div className="flex items-center gap-1">
                  {proj.team.slice(0, 3).map((m, i) => (
                    <div key={i} className="size-5 rounded-full bg-gradient-to-br from-blue-400 to-teal-400 flex items-center justify-center text-white text-[8px] -ml-1 first:ml-0 border border-white">
                      {m}
                    </div>
                  ))}
                </div>
              </div>

              <div className="flex items-center justify-between">
                <span className={`flex items-center gap-1 px-2 py-1 rounded-full text-xs ${s.bg} ${s.color}`}>
                  <SIcon className="size-3" />
                  {s.label}
                </span>
                <span className="text-[10px] text-gray-400 px-2 py-0.5 bg-gray-50 rounded-full">{proj.type}</span>
              </div>
            </div>
          );
        })}
        {shown.length === 0 && (
          <div className="col-span-3 text-center py-12 text-gray-400 text-sm">
            РќСЏРјР° РЅР°РјРµСЂРµРЅРё РїСЂРѕРµРєС‚Рё
          </div>
        )}
      </div>
    </div>
  );
}


// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ
// FILE: src/app/pages/pro/ProContractsPage.tsx
// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ

import { useState } from "react";
import {
  FileText, Plus, Search, Download, Send,
  CheckCircle2, Clock, AlertCircle, Eye, Sparkles, FileSignature,
} from "lucide-react";

const CONTRACTS = [
  { id: "DOG-001", title: "Р”РѕРіРѕРІРѕСЂ СЂРµРјРѕРЅС‚ Р±Р°РЅСЏ вЂ” РњР°СЂРёСЏ РРІР°РЅРѕРІР°", client: "РњР°СЂРёСЏ РРІР°РЅРѕРІР°", value: "12 400 Р»РІ", date: "01 Р°РїСЂ 2026", status: "signed",   project: "СѓР». Р’РёС‚РѕС€Р° 24" },
  { id: "DOG-002", title: "Р”РѕРіРѕРІРѕСЂ СЃС‚СЂРѕРµР¶ РІРёР»Р° вЂ” РџРµС‚СЂРѕРІ & РЎРёРЅРѕРІРµ", client: "РџРµС‚СЂРѕРІ & РЎРёРЅРѕРІРµ", value: "87 200 Р»РІ", date: "15 РјР°СЂС‚ 2026", status: "signed", project: "СЃ. Р“РµСЂРјР°РЅ" },
  { id: "DOG-003", title: "Р”РѕРіРѕРІРѕСЂ РѕС„РёСЃ СЂРµРјРѕРЅС‚ вЂ” Tech Soft OOD",   client: "Tech Soft OOD",   value: "24 900 Р»РІ", date: "20 РјР°СЂС‚ 2026", status: "pending", project: "Р±СѓР». РҐСЂ. Р‘РѕС‚РµРІ" },
  { id: "DOG-004", title: "РћС„РµСЂС‚Р° Р±Р»РѕРє Р±РѕСЏРґРёСЃРІР°РЅРµ вЂ” Р•РЎ РР·С‚РѕРє", client: "Р•РЎ РР·С‚РѕРє", value: "8 700 Р»РІ",  date: "02 Р°РїСЂ 2026", status: "draft",   project: "вЂ”" },
  { id: "DOG-005", title: "Р”РѕРіРѕРІРѕСЂ С‚РµСЂР°РєРѕС‚ РєСѓС…РЅСЏ вЂ” РЎРЅРµР¶Р°РЅР° Р“.",      client: "РЎРЅРµР¶Р°РЅР° Р“РµРѕСЂРіРёРµРІР°",value: "3 200 Р»РІ",  date: "03 Р°РїСЂ 2026", status: "draft",   project: "СѓР». РћРїСЉР»С‡РµРЅСЃРєР° 44" },
];

const STATUS_CFG: Record<string, { label: string; color: string; bg: string; icon: typeof Clock }> = {
  signed:  { label: "РџРѕРґРїРёСЃР°РЅ", color: "text-emerald-700", bg: "bg-emerald-50", icon: CheckCircle2 },
  pending: { label: "РР·С‡Р°РєРІР°",  color: "text-amber-700",   bg: "bg-amber-50",   icon: Clock },
  draft:   { label: "Р§РµСЂРЅРѕРІР°",  color: "text-gray-600",    bg: "bg-gray-100",   icon: AlertCircle },
};

const TEMPLATES = [
  { label: "Р”РѕРіРѕРІРѕСЂ СЂРµРјРѕРЅС‚ Р¶РёР»РёС‰Рµ" },
  { label: "Р”РѕРіРѕРІРѕСЂ РЅРѕРІРѕ СЃС‚СЂРѕРёС‚РµР»СЃС‚РІРѕ" },
  { label: "РЎРїРѕСЂР°Р·СѓРјРµРЅРёРµ Р·Р° РїРѕРґРґСЂСЉР¶РєР°" },
  { label: "РћС„РµСЂС‚Р° СЃ РљРЎРЎ" },
];

export function ProContractsPage() {
  const [q, setQ] = useState("");
  const [aiGen, setAiGen] = useState(false);

  const shown = CONTRACTS.filter(c =>
    c.title.toLowerCase().includes(q.toLowerCase()) ||
    c.client.toLowerCase().includes(q.toLowerCase())
  );

  return (
    <div className="p-5 lg:p-7 space-y-6">
      {/* Header */}
      <div className="flex flex-col sm:flex-row sm:items-center justify-between gap-3">
        <div>
          <h1 className="text-xl text-gray-800">Р”РѕРіРѕРІРѕСЂРё</h1>
          <p className="text-sm text-gray-500 mt-0.5">{CONTRACTS.length} РґРѕРєСѓРјРµРЅС‚Р°</p>
        </div>
        <div className="flex gap-2">
          <button
            onClick={() => setAiGen(true)}
            className="flex items-center gap-2 px-3 py-2 rounded-xl border border-blue-200 text-blue-700 text-sm hover:bg-blue-50 transition-all"
          >
            <Sparkles className="size-4" />
            AI Р”РѕРіРѕРІРѕСЂ
          </button>
          <button className="flex items-center gap-2 px-4 py-2 rounded-xl bg-gradient-to-r from-blue-600 to-teal-600 text-white text-sm hover:from-blue-700 hover:to-teal-700 shadow-md shadow-blue-200 transition-all active:scale-95">
            <Plus className="size-4" />
            РќРѕРІ
          </button>
        </div>
      </div>

      {/* AI gen panel */}
      {aiGen && (
        <div className="bg-gradient-to-r from-blue-50 to-teal-50 border border-blue-200 rounded-2xl p-5">
          <div className="flex items-center gap-2 mb-3">
            <Sparkles className="size-4 text-blue-600" />
            <p className="text-sm text-blue-800">AI РіРµРЅРµСЂРёСЂР° РґРѕРіРѕРІРѕСЂ вЂ” РёР·Р±РµСЂРµС‚Рµ С€Р°Р±Р»РѕРЅ</p>
          </div>
          <div className="grid grid-cols-2 gap-2 mb-3">
            {TEMPLATES.map(t => (
              <button
                key={t.label}
                onClick={() => setAiGen(false)}
                className="text-left px-3 py-2.5 rounded-xl bg-white border border-blue-100 text-sm text-gray-700 hover:border-blue-300 hover:shadow-sm transition-all"
              >
                {t.label}
              </button>
            ))}
          </div>
          <button onClick={() => setAiGen(false)} className="text-xs text-gray-400 hover:text-gray-600">РћС‚РєР°Р·</button>
        </div>
      )}

      {/* Search */}
      <div className="relative w-full sm:w-72">
        <Search className="absolute left-3 top-1/2 -translate-y-1/2 size-3.5 text-gray-400 pointer-events-none" />
        <input
          value={q}
          onChange={e => setQ(e.target.value)}
          placeholder="РўСЉСЂСЃРё РґРѕРіРѕРІРѕСЂвЂ¦"
          className="w-full pl-8 pr-3 py-2 text-sm border border-gray-200 rounded-xl focus:outline-none focus:ring-2 focus:ring-blue-500/20 focus:border-blue-400 transition-all bg-white"
        />
      </div>

      {/* List */}
      <div className="bg-white rounded-2xl border border-gray-100 overflow-hidden">
        <div className="divide-y divide-gray-50">
          {shown.map(c => {
            const s = STATUS_CFG[c.status];
            const SIcon = s.icon;
            return (
              <div key={c.id} className="flex items-center gap-4 px-5 py-4 hover:bg-gray-50/60 transition-colors cursor-pointer group">
                <div className="size-10 rounded-xl bg-blue-50 flex items-center justify-center flex-shrink-0">
                  <FileSignature className="size-5 text-blue-600" />
                </div>
                <div className="flex-1 min-w-0">
                  <p className="text-sm text-gray-800 truncate">{c.title}</p>
                  <p className="text-xs text-gray-400 mt-0.5">{c.client} В· {c.date}</p>
                </div>
                <div className="hidden md:block text-sm text-gray-700 w-28 text-right">{c.value}</div>
                <span className={`flex items-center gap-1 px-2.5 py-1 rounded-full text-xs flex-shrink-0 ${s.bg} ${s.color}`}>
                  <SIcon className="size-3" />
                  {s.label}
                </span>
                <div className="flex items-center gap-1 opacity-0 group-hover:opacity-100 transition-opacity">
                  <button className="size-8 flex items-center justify-center rounded-lg text-gray-400 hover:bg-gray-100 transition-colors">
                    <Eye className="size-4" />
                  </button>
                  <button className="size-8 flex items-center justify-center rounded-lg text-gray-400 hover:bg-gray-100 transition-colors">
                    <Download className="size-4" />
                  </button>
                  <button className="size-8 flex items-center justify-center rounded-lg text-gray-400 hover:bg-gray-100 transition-colors">
                    <Send className="size-4" />
                  </button>
                </div>
              </div>
            );
          })}
        </div>
      </div>
    </div>
  );
}


// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ
// FILE: src/app/pages/pro/ProInvoicesPage.tsx
// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ

import { useState } from "react";
import {
  Receipt, Plus, Search, Download, Send,
  CheckCircle2, Clock, AlertCircle, TrendingUp,
  Euro, Filter, Eye, MoreHorizontal, FileText,
} from "lucide-react";

// в”Ђв”Ђв”Ђ Types в”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђ
type InvStatus = "paid" | "pending" | "overdue" | "draft";

interface Invoice {
  id: string;
  number: string;
  client: string;
  project: string;
  amount: number;
  vat: number;
  date: string;
  due: string;
  status: InvStatus;
}

// в”Ђв”Ђв”Ђ Mock data в”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђ
const INVOICES: Invoice[] = [
  { id: "1", number: "Р¤Рљ-2026-027", client: "РњР°СЂРёСЏ РРІР°РЅРѕРІР°",   project: "Р РµРјРѕРЅС‚ СѓР». Р’РёС‚РѕС€Р° 24",     amount: 10333, vat: 2067, date: "01 Р°РїСЂ 2026", due: "15 Р°РїСЂ", status: "pending" },
  { id: "2", number: "Р¤Рљ-2026-026", client: "РџРµС‚СЂРѕРІ & РЎРёРЅРѕРІРµ", project: "РЎС‚СЂРѕРµР¶ РІРёР»Р° СЃ. Р“РµСЂРјР°РЅ",     amount: 30000, vat: 6000, date: "28 РјР°СЂС‚ 2026", due: "12 Р°РїСЂ", status: "paid"    },
  { id: "3", number: "Р¤Рљ-2026-025", client: "Tech Soft OOD",   project: "РћС„РёСЃ СЂРµРјРѕРЅС‚ РҐСЂ. Р‘РѕС‚РµРІ",    amount: 12450, vat: 2490, date: "25 РјР°СЂС‚ 2026", due: "08 Р°РїСЂ", status: "overdue" },
  { id: "4", number: "Р¤Рљ-2026-024", client: "РҐСЂРёСЃС‚Рѕ РЎС‚РѕРµРІ",    project: "Р“Р°СЂР°Р¶ РєРІ. Р›РѕР·РµРЅРµС†",        amount: 7750,  vat: 1550, date: "20 РјР°СЂС‚ 2026", due: "03 Р°РїСЂ", status: "paid"    },
  { id: "5", number: "Р¤Рљ-2026-023", client: "Р•РЎ РР·С‚РѕРє",        project: "Р‘РѕСЏРґРёСЃРІР°РЅРµ Р¶РёР»РёС‰РµРЅ Р±Р»РѕРє",  amount: 3625,  vat: 725,  date: "15 РјР°СЂС‚ 2026", due: "29 РјР°СЂС‚",status: "overdue" },
  { id: "6", number: "Р¤Рљ-2026-028", client: "РЎРЅРµР¶Р°РЅР° Р“РµРѕСЂРіРёРµРІР°",project: "РўРµСЂР°РєРѕС‚ СѓР». РћРїСЉР»С‡РµРЅСЃРєР°", amount: 2667,  vat: 533,  date: "03 Р°РїСЂ 2026", due: "17 Р°РїСЂ", status: "draft"   },
];

const EXPENSES = [
  { desc: "Р¦РёРјРµРЅС‚ Рё С„Р°СЏРЅСЃ вЂ” Р’РёС‚РѕС€Р° 24",   amount: 2840,  cat: "РњР°С‚РµСЂРёР°Р»Рё",  date: "01 Р°РїСЂ" },
  { desc: "РќР°РµРј СЃРєРµР»Рµ вЂ” Р“РµСЂРјР°РЅ",           amount: 1200,  cat: "РћР±РѕСЂСѓРґРІР°РЅРµ", date: "30 РјР°СЂС‚"},
  { desc: "Р“РѕСЂРёРІРѕ Р·Р° РІР°РЅ",                 amount: 380,   cat: "РўСЂР°РЅСЃРїРѕСЂС‚",  date: "29 РјР°СЂС‚"},
  { desc: "РРЅСЃС‚СЂСѓРјРµРЅС‚Рё вЂ” СЉРіР»РѕС€Р»Р°Р№С„",       amount: 650,   cat: "РћР±РѕСЂСѓРґРІР°РЅРµ", date: "28 РјР°СЂС‚"},
  { desc: "Р‘РѕРё Рё Р»Р°РєРѕРІРµ вЂ” Р‘РѕС‚РµРІ",          amount: 1100,  cat: "РњР°С‚РµСЂРёР°Р»Рё",  date: "26 РјР°СЂС‚"},
];

const STATUS_CFG: Record<InvStatus, { label: string; color: string; bg: string; icon: typeof Clock }> = {
  paid:    { label: "РџР»Р°С‚РµРЅР°",  color: "text-emerald-700", bg: "bg-emerald-50", icon: CheckCircle2 },
  pending: { label: "РР·С‡Р°РєРІР°",  color: "text-amber-700",   bg: "bg-amber-50",   icon: Clock },
  overdue: { label: "РџСЂРѕСЃСЂРѕС‡РµРЅР°",color: "text-red-700",    bg: "bg-red-50",     icon: AlertCircle },
  draft:   { label: "Р§РµСЂРЅРѕРІР°",  color: "text-gray-500",    bg: "bg-gray-100",   icon: FileText },
};

const CAT_COLORS: Record<string, string> = {
  "РњР°С‚РµСЂРёР°Р»Рё":  "text-blue-600 bg-blue-50",
  "РћР±РѕСЂСѓРґРІР°РЅРµ": "text-violet-600 bg-violet-50",
  "РўСЂР°РЅСЃРїРѕСЂС‚":  "text-amber-600 bg-amber-50",
};

// в”Ђв”Ђв”Ђ Component в”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђ
export function ProInvoicesPage() {
  const [tab, setTab] = useState<"invoices" | "expenses">("invoices");
  const [q, setQ] = useState("");
  const [filter, setFilter] = useState<string>("all");

  const totalPaid    = INVOICES.filter(i => i.status === "paid").reduce((s, i) => s + i.amount + i.vat, 0);
  const totalPending = INVOICES.filter(i => i.status === "pending").reduce((s, i) => s + i.amount + i.vat, 0);
  const totalOverdue = INVOICES.filter(i => i.status === "overdue").reduce((s, i) => s + i.amount + i.vat, 0);
  const totalExpenses = EXPENSES.reduce((s, e) => s + e.amount, 0);

  const shown = INVOICES.filter(inv => {
    const mQ = inv.client.toLowerCase().includes(q.toLowerCase()) || inv.number.toLowerCase().includes(q.toLowerCase());
    const mF = filter === "all" || inv.status === filter;
    return mQ && mF;
  });

  return (
    <div className="p-5 lg:p-7 space-y-6">
      {/* Header */}
      <div className="flex flex-col sm:flex-row sm:items-center justify-between gap-3">
        <div>
          <h1 className="text-xl text-gray-800">Р¤Р°РєС‚СѓСЂРё Рё СЂР°Р·С…РѕРґРё</h1>
          <p className="text-sm text-gray-500 mt-0.5">Р¤РёРЅР°РЅСЃРѕРІРё РґРѕРєСѓРјРµРЅС‚Рё РЅР° РЎРљ РЎС‚СЂРѕР№ Р•РћРћР”</p>
        </div>
        <button className="flex items-center gap-2 px-4 py-2.5 rounded-xl bg-gradient-to-r from-blue-600 to-teal-600 text-white text-sm hover:from-blue-700 hover:to-teal-700 shadow-md shadow-blue-200 transition-all active:scale-95 self-start sm:self-auto">
          <Plus className="size-4" />
          РќРѕРІР° С„Р°РєС‚СѓСЂР°
        </button>
      </div>

      {/* KPI bar */}
      <div className="grid grid-cols-2 lg:grid-cols-4 gap-4">
        {[
          { label: "РџР»Р°С‚РµРЅРё",    value: `${totalPaid.toLocaleString("bg-BG")} Р»РІ`,    color: "text-emerald-600", bg: "bg-emerald-50", border: "border-emerald-100" },
          { label: "РР·С‡Р°РєРІР°С‚",   value: `${totalPending.toLocaleString("bg-BG")} Р»РІ`, color: "text-amber-600",   bg: "bg-amber-50",   border: "border-amber-100"   },
          { label: "РџСЂРѕСЃСЂРѕС‡РµРЅРё", value: `${totalOverdue.toLocaleString("bg-BG")} Р»РІ`, color: "text-red-600",     bg: "bg-red-50",     border: "border-red-100"     },
          { label: "Р Р°Р·С…РѕРґРё",    value: `${totalExpenses.toLocaleString("bg-BG")} Р»РІ`,color: "text-blue-600",    bg: "bg-blue-50",    border: "border-blue-100"    },
        ].map(k => (
          <div key={k.label} className={`bg-white rounded-2xl border ${k.border} p-4`}>
            <div className={`size-8 rounded-xl ${k.bg} flex items-center justify-center mb-2`}>
              <Euro className={`size-4 ${k.color}`} />
            </div>
            <p className={`text-lg ${k.color}`}>{k.value}</p>
            <p className="text-xs text-gray-500 mt-0.5">{k.label}</p>
          </div>
        ))}
      </div>

      {/* Tabs */}
      <div className="flex gap-1 bg-gray-100 p-1 rounded-xl w-fit">
        {(["invoices", "expenses"] as const).map(t => (
          <button
            key={t}
            onClick={() => setTab(t)}
            className={`px-4 py-2 rounded-lg text-sm transition-all ${tab === t ? "bg-white text-gray-800 shadow-sm" : "text-gray-500 hover:text-gray-700"}`}
          >
            {t === "invoices" ? "Р¤Р°РєС‚СѓСЂРё" : "Р Р°Р·С…РѕРґРё"}
          </button>
        ))}
      </div>

      {tab === "invoices" && (
        <>
          {/* Filters */}
          <div className="flex flex-wrap gap-2 items-center">
            {(["all","paid","pending","overdue","draft"] as const).map(f => (
              <button
                key={f}
                onClick={() => setFilter(f)}
                className={`px-3 py-1.5 rounded-full text-xs transition-all ${filter === f ? "bg-blue-600 text-white" : "bg-white border border-gray-200 text-gray-600 hover:bg-gray-50"}`}
              >
                {{ all:"Р’СЃРёС‡РєРё", paid:"РџР»Р°С‚РµРЅРё", pending:"РР·С‡Р°РєРІР°С‚", overdue:"РџСЂРѕСЃСЂРѕС‡РµРЅРё", draft:"Р§РµСЂРЅРѕРІРё" }[f]}
              </button>
            ))}
            <div className="flex-1" />
            <div className="relative">
              <Search className="absolute left-3 top-1/2 -translate-y-1/2 size-3.5 text-gray-400 pointer-events-none" />
              <input value={q} onChange={e => setQ(e.target.value)} placeholder="РўСЉСЂСЃРё С„Р°РєС‚СѓСЂР°..." className="pl-8 pr-3 py-1.5 text-xs border border-gray-200 rounded-xl focus:outline-none focus:ring-2 focus:ring-blue-500/20 focus:border-blue-400 bg-white w-44" />
            </div>
          </div>

          {/* Invoice list */}
          <div className="bg-white rounded-2xl border border-gray-100 overflow-hidden">
            <div className="divide-y divide-gray-50">
              {shown.map(inv => {
                const s = STATUS_CFG[inv.status];
                const SIcon = s.icon;
                const total = inv.amount + inv.vat;
                return (
                  <div key={inv.id} className="flex items-center gap-4 px-5 py-4 hover:bg-gray-50/60 transition-colors cursor-pointer group">
                    <div className="size-9 rounded-xl bg-blue-50 flex items-center justify-center flex-shrink-0">
                      <Receipt className="size-4 text-blue-600" />
                    </div>
                    <div className="flex-1 min-w-0">
                      <div className="flex items-center gap-2">
                        <p className="text-sm text-gray-800">{inv.number}</p>
                        <span className={`flex items-center gap-1 px-2 py-0.5 rounded-full text-xs ${s.bg} ${s.color}`}>
                          <SIcon className="size-3" />
                          {s.label}
                        </span>
                      </div>
                      <p className="text-xs text-gray-400 mt-0.5">{inv.client} В· {inv.project}</p>
                    </div>
                    <div className="hidden sm:block text-right">
                      <p className="text-sm text-gray-800">{total.toLocaleString("bg-BG")} Р»РІ</p>
                      <p className="text-xs text-gray-400">СЃ Р”Р”РЎ В· РґРѕ {inv.due}</p>
                    </div>
                    <div className="flex items-center gap-1 opacity-0 group-hover:opacity-100 transition-opacity">
                      <button className="size-8 flex items-center justify-center rounded-lg text-gray-400 hover:bg-gray-100"><Eye className="size-4" /></button>
                      <button className="size-8 flex items-center justify-center rounded-lg text-gray-400 hover:bg-gray-100"><Download className="size-4" /></button>
                      <button className="size-8 flex items-center justify-center rounded-lg text-gray-400 hover:bg-gray-100"><Send className="size-4" /></button>
                    </div>
                  </div>
                );
              })}
              {shown.length === 0 && (
                <div className="text-center py-10 text-sm text-gray-400">РќСЏРјР° РЅР°РјРµСЂРµРЅРё С„Р°РєС‚СѓСЂРё</div>
              )}
            </div>
          </div>
        </>
      )}

      {tab === "expenses" && (
        <div className="space-y-4">
          <div className="bg-white rounded-2xl border border-gray-100 overflow-hidden">
            <div className="px-5 py-3 border-b border-gray-50 flex items-center justify-between">
              <p className="text-sm text-gray-700">Р Р°Р·С…РѕРґРё (РњР°СЂС‚ вЂ” РђРїСЂРёР» 2026)</p>
              <button className="flex items-center gap-1.5 text-xs text-blue-600 hover:text-blue-700">
                <Plus className="size-3" />
                РќРѕРІ СЂР°Р·С…РѕРґ
              </button>
            </div>
            <div className="divide-y divide-gray-50">
              {EXPENSES.map((e, i) => (
                <div key={i} className="flex items-center gap-4 px-5 py-3.5 hover:bg-gray-50/60 transition-colors">
                  <div className="flex-1 min-w-0">
                    <p className="text-sm text-gray-700">{e.desc}</p>
                    <p className="text-xs text-gray-400 mt-0.5">{e.date}</p>
                  </div>
                  <span className={`text-xs px-2 py-0.5 rounded-full ${CAT_COLORS[e.cat] ?? "text-gray-500 bg-gray-100"}`}>{e.cat}</span>
                  <p className="text-sm text-gray-800 w-24 text-right">{e.amount.toLocaleString("bg-BG")} Р»РІ</p>
                  <button className="size-7 flex items-center justify-center rounded-lg text-gray-300 hover:bg-gray-100 hover:text-gray-600 transition-all">
                    <MoreHorizontal className="size-4" />
                  </button>
                </div>
              ))}
            </div>
            <div className="px-5 py-3 border-t border-gray-50 flex items-center justify-between bg-gray-50/50">
              <p className="text-sm text-gray-600">РћР±С‰Рѕ СЂР°Р·С…РѕРґРё</p>
              <p className="text-sm text-gray-800">{totalExpenses.toLocaleString("bg-BG")} Р»РІ</p>
            </div>
          </div>
        </div>
      )}
    </div>
  );
}



// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ
// FILE: src/app/pages/pro/ProWorkersPage.tsx
// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ

import { useState } from "react";
import {
  UserPlus, Search, Phone, Mail, Star, MoreHorizontal,
  HardHat, Wrench, Zap, Paintbrush, CheckCircle2, Clock, XCircle, Filter,
} from "lucide-react";

type Status = "active" | "on_leave" | "inactive";
type Role = "Р—РёРґР°СЂ" | "Р•Р»РµРєС‚СЂРѕС‚РµС…РЅРёРє" | "Р’РѕРґРѕРїСЂРѕРІРѕРґС‡РёРє" | "Р‘РѕСЏРґР¶РёСЏ" | "РџСЂРѕСЂР°Р±" | "РРЅР¶РµРЅРµСЂ" | "РЁРѕС„СЊРѕСЂ";

interface Worker {
  id: string;
  name: string;
  role: Role;
  phone: string;
  email: string;
  rating: number;
  status: Status;
  projects: number;
  salary: number;
  avatar: string;
}

const WORKERS: Worker[] = [
  { id:"1", name:"РРІР°РЅ Р”РёРјРёС‚СЂРѕРІ",    role:"РџСЂРѕСЂР°Р±",        phone:"0888 123 456", email:"ivan.d@sks.bg",     rating:4.9, status:"active",   projects:3, salary:2800, avatar:"РР”" },
  { id:"2", name:"РџР»Р°РјРµРЅ РўРѕРґРѕСЂРѕРІ",   role:"Р—РёРґР°СЂ",         phone:"0876 234 567", email:"plamen.t@sks.bg",   rating:4.7, status:"active",   projects:2, salary:1900, avatar:"РџРў" },
  { id:"3", name:"РљСЂР°СЃРёРјРёСЂ РЎС‚РѕСЏРЅРѕРІ", role:"Р•Р»РµРєС‚СЂРѕС‚РµС…РЅРёРє", phone:"0895 345 678", email:"krasimir@sks.bg",   rating:4.8, status:"active",   projects:2, salary:2100, avatar:"РљРЎ" },
  { id:"4", name:"Р“РµРѕСЂРіРё РџРµС‚РєРѕРІ",    role:"Р’РѕРґРѕРїСЂРѕРІРѕРґС‡РёРє", phone:"0877 456 789", email:"georgi.p@sks.bg",   rating:4.5, status:"on_leave", projects:0, salary:1950, avatar:"Р“Рџ" },
  { id:"5", name:"РЎС‚РµС„Р°РЅ РќРµР№РєРѕРІ",    role:"Р‘РѕСЏРґР¶РёСЏ",       phone:"0888 567 890", email:"stefan.n@sks.bg",   rating:4.6, status:"active",   projects:1, salary:1700, avatar:"РЎРќ" },
  { id:"6", name:"РњРёСЂРѕСЃР»Р°РІ РљРёСЂС‡РµРІ",  role:"РРЅР¶РµРЅРµСЂ",       phone:"0897 678 901", email:"miroslav.k@sks.bg", rating:5.0, status:"active",   projects:3, salary:3200, avatar:"РњРљ" },
  { id:"7", name:"Р‘РѕСЂРёСЃ РђРІСЂР°РјРѕРІ",    role:"РЁРѕС„СЊРѕСЂ",        phone:"0886 789 012", email:"boris.a@sks.bg",    rating:4.4, status:"inactive", projects:0, salary:1600, avatar:"Р‘Рђ" },
  { id:"8", name:"РўРѕРґРѕСЂ Р’Р°СЃРёР»РµРІ",    role:"Р—РёРґР°СЂ",         phone:"0876 890 123", email:"todor.v@sks.bg",    rating:4.7, status:"active",   projects:2, salary:1900, avatar:"РўР’" },
];

const ROLE_ICONS: Record<Role, typeof HardHat> = {
  "Р—РёРґР°СЂ": HardHat, "Р•Р»РµРєС‚СЂРѕС‚РµС…РЅРёРє": Zap, "Р’РѕРґРѕРїСЂРѕРІРѕРґС‡РёРє": Wrench,
  "Р‘РѕСЏРґР¶РёСЏ": Paintbrush, "РџСЂРѕСЂР°Р±": HardHat, "РРЅР¶РµРЅРµСЂ": Wrench, "РЁРѕС„СЊРѕСЂ": HardHat,
};
const ROLE_COLORS: Record<Role, string> = {
  "Р—РёРґР°СЂ":"text-amber-600 bg-amber-50","Р•Р»РµРєС‚СЂРѕС‚РµС…РЅРёРє":"text-yellow-600 bg-yellow-50",
  "Р’РѕРґРѕРїСЂРѕРІРѕРґС‡РёРє":"text-blue-600 bg-blue-50","Р‘РѕСЏРґР¶РёСЏ":"text-pink-600 bg-pink-50",
  "РџСЂРѕСЂР°Р±":"text-orange-600 bg-orange-50","РРЅР¶РµРЅРµСЂ":"text-violet-600 bg-violet-50","РЁРѕС„СЊРѕСЂ":"text-teal-600 bg-teal-50",
};
const STATUS_CFG: Record<Status, { label: string; color: string; bg: string; icon: typeof Clock }> = {
  active:   { label:"РђРєС‚РёРІРµРЅ",   color:"text-emerald-700", bg:"bg-emerald-50", icon: CheckCircle2 },
  on_leave: { label:"Р’ РѕС‚РїСѓСЃРє",  color:"text-amber-700",   bg:"bg-amber-50",   icon: Clock },
  inactive: { label:"РќРµР°РєС‚РёРІРµРЅ", color:"text-gray-500",    bg:"bg-gray-100",   icon: XCircle },
};
const AVATAR_COLORS = [
  "from-blue-500 to-violet-600","from-teal-500 to-blue-600","from-orange-500 to-red-600",
  "from-emerald-500 to-teal-600","from-violet-500 to-pink-600","from-amber-500 to-orange-600",
  "from-pink-500 to-rose-600","from-indigo-500 to-blue-600",
];

export function ProWorkersPage() {
  const [q, setQ] = useState("");
  const [filter, setFilter] = useState<string>("all");

  const shown = WORKERS.filter(w => {
    const mQ = w.name.toLowerCase().includes(q.toLowerCase()) || w.role.toLowerCase().includes(q.toLowerCase());
    const mF = filter === "all" || w.status === filter;
    return mQ && mF;
  });

  const active   = WORKERS.filter(w => w.status === "active").length;
  const onLeave  = WORKERS.filter(w => w.status === "on_leave").length;
  const inactive = WORKERS.filter(w => w.status === "inactive").length;
  const totalSalary = WORKERS.filter(w => w.status === "active").reduce((s,w)=>s+w.salary,0);

  return (
    <div className="p-5 lg:p-7 space-y-6">
      {/* Header */}
      <div className="flex flex-col sm:flex-row sm:items-center justify-between gap-3">
        <div>
          <h1 className="text-xl text-gray-800">Р Р°Р±РѕС‚РЅРёС†Рё</h1>
          <p className="text-sm text-gray-500 mt-0.5">РЈРїСЂР°РІР»РµРЅРёРµ РЅР° РµРєРёРїР° вЂ” {WORKERS.length} СЃР»СѓР¶РёС‚РµР»Рё</p>
        </div>
        <button className="flex items-center gap-2 px-4 py-2.5 rounded-xl bg-gradient-to-r from-blue-600 to-teal-600 text-white text-sm hover:from-blue-700 hover:to-teal-700 shadow-md shadow-blue-200 transition-all active:scale-95 self-start sm:self-auto">
          <UserPlus className="size-4" />
          Р”РѕР±Р°РІРё СЂР°Р±РѕС‚РЅРёРє
        </button>
      </div>

      {/* KPIs */}
      <div className="grid grid-cols-2 lg:grid-cols-4 gap-4">
        {[
          { label:"РђРєС‚РёРІРЅРё",          value: active,                            color:"text-emerald-600", bg:"bg-emerald-50", border:"border-emerald-100" },
          { label:"Р’ РѕС‚РїСѓСЃРє",          value: onLeave,                           color:"text-amber-600",   bg:"bg-amber-50",   border:"border-amber-100" },
          { label:"РќРµР°РєС‚РёРІРЅРё",         value: inactive,                          color:"text-gray-500",    bg:"bg-gray-100",   border:"border-gray-200" },
          { label:"Р Р°Р·С…РѕРґРё / РјРµСЃРµС†",   value:`${totalSalary.toLocaleString("bg-BG")} Р»РІ`, color:"text-blue-600", bg:"bg-blue-50", border:"border-blue-100" },
        ].map(k => (
          <div key={k.label} className={`bg-white rounded-2xl border ${k.border} p-4`}>
            <p className={`text-xl ${k.color}`}>{k.value}</p>
            <p className="text-xs text-gray-500 mt-0.5">{k.label}</p>
          </div>
        ))}
      </div>

      {/* Filters + search */}
      <div className="flex flex-wrap gap-2 items-center">
        {(["all","active","on_leave","inactive"] as const).map(f => (
          <button key={f} onClick={() => setFilter(f)}
            className={`px-3 py-1.5 rounded-full text-xs transition-all ${filter===f ? "bg-blue-600 text-white" : "bg-white border border-gray-200 text-gray-600 hover:bg-gray-50"}`}>
            {{ all:"Р’СЃРёС‡РєРё", active:"РђРєС‚РёРІРЅРё", on_leave:"Р’ РѕС‚РїСѓСЃРє", inactive:"РќРµР°РєС‚РёРІРЅРё" }[f]}
          </button>
        ))}
        <div className="flex-1" />
        <div className="relative">
          <Search className="absolute left-3 top-1/2 -translate-y-1/2 size-3.5 text-gray-400 pointer-events-none" />
          <input value={q} onChange={e=>setQ(e.target.value)} placeholder="РўСЉСЂСЃРё СЂР°Р±РѕС‚РЅРёРє..." className="pl-8 pr-3 py-1.5 text-xs border border-gray-200 rounded-xl focus:outline-none focus:ring-2 focus:ring-blue-500/20 focus:border-blue-400 bg-white w-44" />
        </div>
      </div>

      {/* Workers grid */}
      <div className="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4 gap-4">
        {shown.map((w, i) => {
          const s = STATUS_CFG[w.status];
          const SIcon = s.icon;
          const RIcon = ROLE_ICONS[w.role];
          const roleColor = ROLE_COLORS[w.role];
          return (
            <div key={w.id} className="bg-white rounded-2xl border border-gray-100 p-4 hover:shadow-md hover:-translate-y-0.5 transition-all cursor-pointer group">
              <div className="flex items-start justify-between mb-3">
                <div className={`size-12 rounded-2xl bg-gradient-to-br ${AVATAR_COLORS[i % AVATAR_COLORS.length]} flex items-center justify-center text-white text-sm`}>
                  {w.avatar}
                </div>
                <div className="flex items-center gap-1">
                  <span className={`flex items-center gap-1 px-2 py-0.5 rounded-full text-xs ${s.bg} ${s.color}`}>
                    <SIcon className="size-3" />{s.label}
                  </span>
                  <button className="size-7 flex items-center justify-center rounded-lg text-gray-300 hover:bg-gray-100 hover:text-gray-500 transition-all">
                    <MoreHorizontal className="size-4" />
                  </button>
                </div>
              </div>
              <p className="text-sm text-gray-800">{w.name}</p>
              <div className={`inline-flex items-center gap-1.5 mt-1 px-2 py-0.5 rounded-full text-xs ${roleColor}`}>
                <RIcon className="size-3" />{w.role}
              </div>
              <div className="mt-3 pt-3 border-t border-gray-50 space-y-1.5">
                <div className="flex items-center gap-2">
                  <Phone className="size-3.5 text-gray-400 flex-shrink-0" />
                  <span className="text-xs text-gray-500">{w.phone}</span>
                </div>
                <div className="flex items-center gap-2">
                  <Mail className="size-3.5 text-gray-400 flex-shrink-0" />
                  <span className="text-xs text-gray-500 truncate">{w.email}</span>
                </div>
              </div>
              <div className="mt-3 flex items-center justify-between">
                <div className="flex items-center gap-1">
                  <Star className="size-3.5 text-amber-400 fill-amber-400" />
                  <span className="text-xs text-gray-600">{w.rating}</span>
                </div>
                <div className="text-right">
                  <p className="text-xs text-gray-400">{w.projects} РїСЂРѕРµРєС‚Р°</p>
                </div>
              </div>
            </div>
          );
        })}
      </div>
    </div>
  );
}



// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ
// FILE: src/app/pages/pro/ProDocumentsProPage.tsx
// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ

import { useState } from "react";
import {
  Upload, Search, FolderOpen, File, FileText, Image,
  Download, Eye, MoreHorizontal, Plus, Grid3X3, List,
  Clock, Star, Trash2, Share2,
} from "lucide-react";

type DocType = "pdf" | "doc" | "xls" | "img" | "dwg" | "zip";

interface Doc {
  id: string;
  name: string;
  type: DocType;
  size: string;
  project: string;
  date: string;
  starred: boolean;
}

const DOCS: Doc[] = [
  { id:"1", name:"РљРЎРЎ_Р’РёС‚РѕС€Р°_24_С„РёРЅР°Р».xlsx",        type:"xls", size:"48 KB",  project:"Р’РёС‚РѕС€Р° 24",      date:"03 Р°РїСЂ 2026", starred:true  },
  { id:"2", name:"Р”РѕРіРѕРІРѕСЂ_РџРµС‚СЂРѕРІ_РЎРёРЅРѕРІРµ_v2.pdf",     type:"pdf", size:"124 KB", project:"СЃ. Р“РµСЂРјР°РЅ",      date:"01 Р°РїСЂ 2026", starred:true  },
  { id:"3", name:"РўРµС…РЅРёС‡РµСЃРєРё_РїСЂРѕРµРєС‚_Р“РµСЂРјР°РЅ.dwg",     type:"dwg", size:"3.2 MB", project:"СЃ. Р“РµСЂРјР°РЅ",      date:"28 РјР°СЂС‚ 2026",starred:false },
  { id:"4", name:"РЎРЅРёРјРєРё_РїСЂРѕРіСЂРµСЃ_Р‘РѕС‚РµРІ.zip",         type:"zip", size:"22 MB",  project:"РҐСЂ. Р‘РѕС‚РµРІ",      date:"26 РјР°СЂС‚ 2026",starred:false },
  { id:"5", name:"РђРєС‚ 16_Р›РѕР·РµРЅРµС†.pdf",               type:"pdf", size:"89 KB",  project:"РєРІ. Р›РѕР·РµРЅРµС†",    date:"25 РјР°СЂС‚ 2026",starred:true  },
  { id:"6", name:"РћС„РµСЂС‚Р°_Tech_Soft_OOD.docx",        type:"doc", size:"67 KB",  project:"РҐСЂ. Р‘РѕС‚РµРІ",      date:"24 РјР°СЂС‚ 2026",starred:false },
  { id:"7", name:"Р§РµСЂС‚РµР¶Рё_РћРїСЉР»С‡РµРЅСЃРєР°_44.dwg",        type:"dwg", size:"5.8 MB", project:"РћРїСЉР»С‡РµРЅСЃРєР° 44",  date:"22 РјР°СЂС‚ 2026",starred:false },
  { id:"8", name:"РРЅСЃРїРµРєС†РёСЏ_РјР°СЂС‚_2026.pdf",           type:"pdf", size:"210 KB", project:"Р’СЃРёС‡РєРё",         date:"20 РјР°СЂС‚ 2026",starred:false },
  { id:"9", name:"Р’РёР·СѓР°Р»РёР·Р°С†РёСЏ_С„Р°СЃР°РґР°_Р“РµСЂРјР°РЅ.png",   type:"img", size:"4.1 MB", project:"СЃ. Р“РµСЂРјР°РЅ",      date:"18 РјР°СЂС‚ 2026",starred:true  },
  { id:"10",name:"Р Р°Р·СЂРµС€РёС‚РµР»РЅРѕ_СЃС‚СЂРѕРµР¶_Р’РёС‚РѕС€Р°.pdf",   type:"pdf", size:"156 KB", project:"Р’РёС‚РѕС€Р° 24",      date:"15 РјР°СЂС‚ 2026",starred:false },
];

const FOLDERS = ["Р’СЃРёС‡РєРё РґРѕРєСѓРјРµРЅС‚Рё","Р”РѕРіРѕРІРѕСЂРё","РљРЎРЎ","Р§РµСЂС‚РµР¶Рё","РЎРЅРёРјРєРё","РђРєС‚РѕРІРµ","РћС„РµСЂС‚Рё"];

const TYPE_CFG: Record<DocType, { color: string; bg: string; label: string }> = {
  pdf: { color:"text-red-600",    bg:"bg-red-50",    label:"PDF"  },
  doc: { color:"text-blue-600",   bg:"bg-blue-50",   label:"DOC"  },
  xls: { color:"text-emerald-600",bg:"bg-emerald-50",label:"XLS"  },
  img: { color:"text-violet-600", bg:"bg-violet-50", label:"IMG"  },
  dwg: { color:"text-amber-600",  bg:"bg-amber-50",  label:"DWG"  },
  zip: { color:"text-gray-600",   bg:"bg-gray-100",  label:"ZIP"  },
};

const TYPE_ICONS: Record<DocType, typeof File> = {
  pdf: FileText, doc: FileText, xls: File, img: Image, dwg: File, zip: File,
};

export function ProDocumentsProPage() {
  const [q, setQ] = useState("");
  const [folder, setFolder] = useState("Р’СЃРёС‡РєРё РґРѕРєСѓРјРµРЅС‚Рё");
  const [view, setView] = useState<"grid"|"list">("list");
  const [docs, setDocs] = useState(DOCS);

  const toggleStar = (id: string) =>
    setDocs(prev => prev.map(d => d.id===id ? {...d,starred:!d.starred} : d));

  const shown = docs.filter(d => {
    const mQ = d.name.toLowerCase().includes(q.toLowerCase()) || d.project.toLowerCase().includes(q.toLowerCase());
    const mF = folder === "Р’СЃРёС‡РєРё РґРѕРєСѓРјРµРЅС‚Рё" ||
      (folder === "Р”РѕРіРѕРІРѕСЂРё" && d.name.toLowerCase().includes("РґРѕРіРѕРІРѕСЂ")) ||
      (folder === "РљРЎРЎ"      && d.name.toLowerCase().includes("РєСЃ")) ||
      (folder === "Р§РµСЂС‚РµР¶Рё"  && d.type === "dwg") ||
      (folder === "РЎРЅРёРјРєРё"   && d.type === "img") ||
      (folder === "РђРєС‚РѕРІРµ"   && d.name.toLowerCase().includes("Р°РєС‚")) ||
      (folder === "РћС„РµСЂС‚Рё"   && d.name.toLowerCase().includes("РѕС„РµСЂС‚"));
    return mQ && mF;
  });

  return (
    <div className="p-5 lg:p-7 space-y-5">
      {/* Header */}
      <div className="flex flex-col sm:flex-row sm:items-center justify-between gap-3">
        <div>
          <h1 className="text-xl text-gray-800">Р”РѕРєСѓРјРµРЅС‚Рё</h1>
          <p className="text-sm text-gray-500 mt-0.5">{DOCS.length} С„Р°Р№Р»Р° В· {docs.filter(d=>d.starred).length} РјР°СЂРєРёСЂР°РЅРё СЃ в…</p>
        </div>
        <div className="flex items-center gap-2 self-start sm:self-auto">
          <button className="flex items-center gap-2 px-3 py-2 rounded-xl border border-gray-200 text-sm text-gray-600 bg-white hover:bg-gray-50 transition-all">
            <Upload className="size-4" />
            РљР°С‡Рё
          </button>
          <button className="flex items-center gap-2 px-4 py-2 rounded-xl bg-gradient-to-r from-blue-600 to-teal-600 text-white text-sm hover:from-blue-700 hover:to-teal-700 shadow-md shadow-blue-200 transition-all active:scale-95">
            <Plus className="size-4" />
            РќРѕРІР° РїР°РїРєР°
          </button>
        </div>
      </div>

      <div className="flex flex-col lg:flex-row gap-5">
        {/* Folder tree */}
        <div className="lg:w-52 flex-shrink-0 bg-white rounded-2xl border border-gray-100 p-3 h-fit">
          <p className="text-xs text-gray-400 px-2 pb-2">РџРђРџРљР</p>
          {FOLDERS.map(f => (
            <button key={f} onClick={() => setFolder(f)}
              className={`w-full flex items-center gap-2.5 px-3 py-2 rounded-xl text-sm transition-all ${folder===f ? "bg-blue-50 text-blue-700" : "text-gray-600 hover:bg-gray-50"}`}>
              <FolderOpen className={`size-4 flex-shrink-0 ${folder===f ? "text-blue-500" : "text-amber-400"}`} />
              {f}
            </button>
          ))}
        </div>

        {/* Main panel */}
        <div className="flex-1 min-w-0 space-y-3">
          {/* Toolbar */}
          <div className="flex items-center gap-2">
            <div className="relative flex-1 max-w-xs">
              <Search className="absolute left-3 top-1/2 -translate-y-1/2 size-3.5 text-gray-400 pointer-events-none" />
              <input value={q} onChange={e=>setQ(e.target.value)} placeholder="РўСЉСЂСЃРё С„Р°Р№Р»..." className="pl-8 pr-3 py-2 text-xs border border-gray-200 rounded-xl focus:outline-none focus:ring-2 focus:ring-blue-500/20 focus:border-blue-400 bg-white w-full" />
            </div>
            <div className="flex-1" />
            <div className="flex items-center gap-1 bg-gray-100 p-1 rounded-xl">
              <button onClick={() => setView("list")} className={`size-8 flex items-center justify-center rounded-lg transition-all ${view==="list" ? "bg-white shadow-sm text-blue-600" : "text-gray-500 hover:text-gray-700"}`}>
                <List className="size-4" />
              </button>
              <button onClick={() => setView("grid")} className={`size-8 flex items-center justify-center rounded-lg transition-all ${view==="grid" ? "bg-white shadow-sm text-blue-600" : "text-gray-500 hover:text-gray-700"}`}>
                <Grid3X3 className="size-4" />
              </button>
            </div>
          </div>

          {/* Documents */}
          {view === "list" ? (
            <div className="bg-white rounded-2xl border border-gray-100 overflow-hidden">
              <div className="divide-y divide-gray-50">
                {shown.map(d => {
                  const cfg = TYPE_CFG[d.type];
                  const DIcon = TYPE_ICONS[d.type];
                  return (
                    <div key={d.id} className="flex items-center gap-3 px-4 py-3 hover:bg-gray-50/60 transition-colors group cursor-pointer">
                      <div className={`size-9 rounded-xl ${cfg.bg} flex items-center justify-center flex-shrink-0`}>
                        <DIcon className={`size-4 ${cfg.color}`} />
                      </div>
                      <div className="flex-1 min-w-0">
                        <p className="text-sm text-gray-700 truncate">{d.name}</p>
                        <p className="text-xs text-gray-400">{d.project} В· {d.size}</p>
                      </div>
                      <div className="hidden sm:flex items-center gap-1.5">
                        <Clock className="size-3.5 text-gray-300" />
                        <span className="text-xs text-gray-400">{d.date}</span>
                      </div>
                      <span className={`text-[10px] px-1.5 py-0.5 rounded-full ${cfg.bg} ${cfg.color}`}>{cfg.label}</span>
                      <div className="flex items-center gap-0.5 opacity-0 group-hover:opacity-100 transition-opacity">
                        <button onClick={()=>toggleStar(d.id)} className={`size-7 flex items-center justify-center rounded-lg transition-all ${d.starred ? "text-amber-400" : "text-gray-300 hover:text-amber-400"}`}>
                          <Star className={`size-3.5 ${d.starred ? "fill-amber-400" : ""}`} />
                        </button>
                        <button className="size-7 flex items-center justify-center rounded-lg text-gray-300 hover:text-blue-500 transition-all"><Eye className="size-3.5" /></button>
                        <button className="size-7 flex items-center justify-center rounded-lg text-gray-300 hover:text-blue-500 transition-all"><Download className="size-3.5" /></button>
                        <button className="size-7 flex items-center justify-center rounded-lg text-gray-300 hover:text-gray-500 transition-all"><MoreHorizontal className="size-3.5" /></button>
                      </div>
                    </div>
                  );
                })}
                {shown.length === 0 && (
                  <div className="text-center py-10 text-sm text-gray-400">РќСЏРјР° РЅР°РјРµСЂРµРЅРё С„Р°Р№Р»РѕРІРµ</div>
                )}
              </div>
            </div>
          ) : (
            <div className="grid grid-cols-2 sm:grid-cols-3 lg:grid-cols-4 gap-3">
              {shown.map(d => {
                const cfg = TYPE_CFG[d.type];
                const DIcon = TYPE_ICONS[d.type];
                return (
                  <div key={d.id} className="bg-white rounded-2xl border border-gray-100 p-4 hover:shadow-md hover:-translate-y-0.5 transition-all cursor-pointer group relative">
                    <button onClick={()=>toggleStar(d.id)} className={`absolute top-2.5 right-2.5 size-6 flex items-center justify-center rounded-lg transition-all ${d.starred ? "text-amber-400" : "text-gray-200 group-hover:text-gray-400"}`}>
                      <Star className={`size-3.5 ${d.starred ? "fill-amber-400" : ""}`} />
                    </button>
                    <div className={`size-10 rounded-xl ${cfg.bg} flex items-center justify-center mb-3`}>
                      <DIcon className={`size-5 ${cfg.color}`} />
                    </div>
                    <p className="text-xs text-gray-700 truncate pr-4">{d.name}</p>
                    <p className="text-[10px] text-gray-400 mt-1">{d.size}</p>
                    <div className="mt-2 flex items-center justify-between">
                      <span className={`text-[10px] px-1.5 py-0.5 rounded-full ${cfg.bg} ${cfg.color}`}>{cfg.label}</span>
                    </div>
                  </div>
                );
              })}
            </div>
          )}
        </div>
      </div>
    </div>
  );
}



// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ
// FILE: src/app/pages/pro/ProAssetsPage.tsx
// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ

import { useState } from "react";
import {
  Plus, Search, Truck, Wrench, Zap, Package,
  CheckCircle2, AlertCircle, Clock, MoreHorizontal, QrCode,
} from "lucide-react";

type AssetStatus = "available" | "in_use" | "maintenance" | "broken";
type AssetCat = "РњР°С€РёРЅРё" | "РРЅСЃС‚СЂСѓРјРµРЅС‚Рё" | "РџСЂРµРІРѕР·РЅРё СЃСЂРµРґСЃС‚РІР°" | "РњР°С‚РµСЂРёР°Р»Рё";

interface Asset {
  id: string;
  name: string;
  category: AssetCat;
  status: AssetStatus;
  location: string;
  assignedTo: string;
  lastCheck: string;
  value: number;
}

const ASSETS: Asset[] = [
  { id:"1",  name:"РЎРєРµР»Рµ вЂ” РєРѕРјРїР»РµРєС‚ 60mВІ",  category:"РњР°С€РёРЅРё",           status:"in_use",    location:"СЃ. Р“РµСЂРјР°РЅ",     assignedTo:"РџР»Р°РјРµРЅ РўРѕРґРѕСЂРѕРІ",   lastCheck:"01 Р°РїСЂ", value:4500  },
  { id:"2",  name:"РњРёРєСЃРµСЂ Р±РµС‚РѕРЅ 250L",       category:"РњР°С€РёРЅРё",           status:"available", location:"РЎРєР»Р°Рґ",         assignedTo:"вЂ”",                lastCheck:"30 РјР°СЂС‚",value:3200  },
  { id:"3",  name:"РЄРіР»РѕС€Р»Р°Р№С„ Bosch 125mm",   category:"РРЅСЃС‚СЂСѓРјРµРЅС‚Рё",      status:"in_use",    location:"Р’РёС‚РѕС€Р° 24",     assignedTo:"РЎС‚РµС„Р°РЅ РќРµР№РєРѕРІ",    lastCheck:"28 РјР°СЂС‚",value:450   },
  { id:"4",  name:"РџРµСЂР°Р»РЅСЏ РјР°Р·РёР»РєР°",         category:"РњР°С€РёРЅРё",           status:"maintenance",location:"РЎРµСЂРІРёР·",       assignedTo:"вЂ”",                lastCheck:"25 РјР°СЂС‚",value:2800  },
  { id:"5",  name:"Р’Р°РЅ VW Crafter",          category:"РџСЂРµРІРѕР·РЅРё СЃСЂРµРґСЃС‚РІР°",status:"in_use",    location:"РњР°СЂС€СЂСѓС‚",       assignedTo:"Р‘РѕСЂРёСЃ РђРІСЂР°РјРѕРІ",    lastCheck:"20 РјР°СЂС‚",value:28000 },
  { id:"6",  name:"Р‘РѕСЂРјР°С€РёРЅР° Hilti TE 6-A",  category:"РРЅСЃС‚СЂСѓРјРµРЅС‚Рё",      status:"available", location:"РЎРєР»Р°Рґ",         assignedTo:"вЂ”",                lastCheck:"18 РјР°СЂС‚",value:1200  },
  { id:"7",  name:"РњРµСЂС†РµРґРµСЃ Sprinter",       category:"РџСЂРµРІРѕР·РЅРё СЃСЂРµРґСЃС‚РІР°",status:"available", location:"Р‘Р°Р·Р°",          assignedTo:"вЂ”",                lastCheck:"15 РјР°СЂС‚",value:35000 },
  { id:"8",  name:"Р›Р°Р·РµСЂРµРЅ РЅРёРІРµР»РёСЂ Leica",   category:"РРЅСЃС‚СЂСѓРјРµРЅС‚Рё",      status:"in_use",    location:"РћРїСЉР»С‡РµРЅСЃРєР° 44", assignedTo:"РњРёСЂРѕСЃР»Р°РІ РљРёСЂС‡РµРІ",  lastCheck:"12 РјР°СЂС‚",value:2100  },
  { id:"9",  name:"Р•Р». С‚Р°Р±Р»Рѕ РІСЂРµРјРµРЅРЅРѕ",      category:"РњР°С€РёРЅРё",           status:"broken",    location:"РЎРєР»Р°Рґ",         assignedTo:"вЂ”",                lastCheck:"10 РјР°СЂС‚",value:800   },
  { id:"10", name:"Р¦РёРјРµРЅС‚РѕРІ СЃРєР»Р°Рґ 5С‚",       category:"РњР°С‚РµСЂРёР°Р»Рё",        status:"available", location:"Р‘Р°Р·Р°",          assignedTo:"вЂ”",                lastCheck:"08 РјР°СЂС‚",value:3000  },
];

const STATUS_CFG: Record<AssetStatus, { label: string; color: string; bg: string; icon: typeof Clock }> = {
  available:   { label:"РќР°Р»РёС‡РµРЅ",     color:"text-emerald-700", bg:"bg-emerald-50", icon: CheckCircle2 },
  in_use:      { label:"Р’ СѓРїРѕС‚СЂРµР±Р°",  color:"text-blue-700",    bg:"bg-blue-50",    icon: Clock },
  maintenance: { label:"РЎРµСЂРІРёР·",      color:"text-amber-700",   bg:"bg-amber-50",   icon: Wrench },
  broken:      { label:"РџРѕРІСЂРµРґРµРЅ",    color:"text-red-700",     bg:"bg-red-50",     icon: AlertCircle },
};

const CAT_ICONS: Record<AssetCat, typeof Wrench> = {
  "РњР°С€РёРЅРё": Package, "РРЅСЃС‚СЂСѓРјРµРЅС‚Рё": Wrench, "РџСЂРµРІРѕР·РЅРё СЃСЂРµРґСЃС‚РІР°": Truck, "РњР°С‚РµСЂРёР°Р»Рё": Package,
};
const CAT_COLORS: Record<AssetCat, string> = {
  "РњР°С€РёРЅРё":"text-violet-600 bg-violet-50","РРЅСЃС‚СЂСѓРјРµРЅС‚Рё":"text-blue-600 bg-blue-50",
  "РџСЂРµРІРѕР·РЅРё СЃСЂРµРґСЃС‚РІР°":"text-teal-600 bg-teal-50","РњР°С‚РµСЂРёР°Р»Рё":"text-amber-600 bg-amber-50",
};

export function ProAssetsPage() {
  const [q, setQ] = useState("");
  const [filter, setFilter] = useState<string>("all");
  const [cat, setCat] = useState<string>("all");

  const avail   = ASSETS.filter(a=>a.status==="available").length;
  const inUse   = ASSETS.filter(a=>a.status==="in_use").length;
  const maint   = ASSETS.filter(a=>a.status==="maintenance").length;
  const broken  = ASSETS.filter(a=>a.status==="broken").length;
  const totalVal = ASSETS.reduce((s,a)=>s+a.value,0);

  const shown = ASSETS.filter(a => {
    const mQ  = a.name.toLowerCase().includes(q.toLowerCase()) || a.assignedTo.toLowerCase().includes(q.toLowerCase());
    const mF  = filter === "all" || a.status === filter;
    const mC  = cat === "all" || a.category === cat;
    return mQ && mF && mC;
  });

  return (
    <div className="p-5 lg:p-7 space-y-6">
      {/* Header */}
      <div className="flex flex-col sm:flex-row sm:items-center justify-between gap-3">
        <div>
          <h1 className="text-xl text-gray-800">РђРєС‚РёРІРё</h1>
          <p className="text-sm text-gray-500 mt-0.5">РћР±РѕСЂСѓРґРІР°РЅРµ, РёРЅСЃС‚СЂСѓРјРµРЅС‚Рё Рё РїСЂРµРІРѕР·РЅРё СЃСЂРµРґСЃС‚РІР°</p>
        </div>
        <div className="flex items-center gap-2 self-start sm:self-auto">
          <button className="flex items-center gap-2 px-3 py-2 rounded-xl border border-gray-200 text-sm text-gray-600 bg-white hover:bg-gray-50 transition-all">
            <QrCode className="size-4" />
            QR СЃРєР°РЅ
          </button>
          <button className="flex items-center gap-2 px-4 py-2 rounded-xl bg-gradient-to-r from-blue-600 to-teal-600 text-white text-sm hover:from-blue-700 hover:to-teal-700 shadow-md shadow-blue-200 transition-all active:scale-95">
            <Plus className="size-4" />
            Р”РѕР±Р°РІРё Р°РєС‚РёРІ
          </button>
        </div>
      </div>

      {/* KPIs */}
      <div className="grid grid-cols-2 lg:grid-cols-5 gap-4">
        {[
          { label:"РќР°Р»РёС‡РЅРё",       value: avail,  color:"text-emerald-600", border:"border-emerald-100" },
          { label:"Р’ СѓРїРѕС‚СЂРµР±Р°",    value: inUse,  color:"text-blue-600",    border:"border-blue-100" },
          { label:"РЎРµСЂРІРёР·",        value: maint,  color:"text-amber-600",   border:"border-amber-100" },
          { label:"РџРѕРІСЂРµРґРµРЅРё",     value: broken, color:"text-red-600",     border:"border-red-100" },
          { label:"РћР±С‰Р° СЃС‚РѕР№РЅРѕСЃС‚", value:`${totalVal.toLocaleString("bg-BG")} Р»РІ`, color:"text-violet-600", border:"border-violet-100" },
        ].map(k => (
          <div key={k.label} className={`bg-white rounded-2xl border ${k.border} p-4`}>
            <p className={`text-xl ${k.color}`}>{k.value}</p>
            <p className="text-xs text-gray-500 mt-0.5">{k.label}</p>
          </div>
        ))}
      </div>

      {/* Filters */}
      <div className="flex flex-wrap gap-2 items-center">
        {(["all","available","in_use","maintenance","broken"] as const).map(f => (
          <button key={f} onClick={() => setFilter(f)}
            className={`px-3 py-1.5 rounded-full text-xs transition-all ${filter===f ? "bg-blue-600 text-white" : "bg-white border border-gray-200 text-gray-600 hover:bg-gray-50"}`}>
            {{ all:"Р’СЃРёС‡РєРё", available:"РќР°Р»РёС‡РЅРё", in_use:"Р’ СѓРїРѕС‚СЂРµР±Р°", maintenance:"РЎРµСЂРІРёР·", broken:"РџРѕРІСЂРµРґРµРЅРё" }[f]}
          </button>
        ))}
        <div className="w-px h-4 bg-gray-200 mx-1" />
        {(["all","РњР°С€РёРЅРё","РРЅСЃС‚СЂСѓРјРµРЅС‚Рё","РџСЂРµРІРѕР·РЅРё СЃСЂРµРґСЃС‚РІР°","РњР°С‚РµСЂРёР°Р»Рё"] as const).map(c => (
          <button key={c} onClick={() => setCat(c)}
            className={`px-3 py-1.5 rounded-full text-xs transition-all ${cat===c ? "bg-teal-600 text-white" : "bg-white border border-gray-200 text-gray-600 hover:bg-gray-50"}`}>
            {c === "all" ? "Р’СЃРёС‡РєРё РєР°С‚РµРіРѕСЂРёРё" : c}
          </button>
        ))}
        <div className="flex-1" />
        <div className="relative">
          <Search className="absolute left-3 top-1/2 -translate-y-1/2 size-3.5 text-gray-400 pointer-events-none" />
          <input value={q} onChange={e=>setQ(e.target.value)} placeholder="РўСЉСЂСЃРё Р°РєС‚РёРІ..." className="pl-8 pr-3 py-1.5 text-xs border border-gray-200 rounded-xl focus:outline-none focus:ring-2 focus:ring-blue-500/20 focus:border-blue-400 bg-white w-44" />
        </div>
      </div>

      {/* Assets table */}
      <div className="bg-white rounded-2xl border border-gray-100 overflow-hidden">
        <div className="divide-y divide-gray-50">
          {shown.map(a => {
            const s = STATUS_CFG[a.status];
            const SIcon = s.icon;
            const CIcon = CAT_ICONS[a.category];
            const catColor = CAT_COLORS[a.category];
            return (
              <div key={a.id} className="flex items-center gap-4 px-5 py-3.5 hover:bg-gray-50/60 transition-colors cursor-pointer group">
                <div className={`size-9 rounded-xl flex items-center justify-center flex-shrink-0 ${catColor.split(" ")[1]}`}>
                  <CIcon className={`size-4 ${catColor.split(" ")[0]}`} />
                </div>
                <div className="flex-1 min-w-0">
                  <p className="text-sm text-gray-700">{a.name}</p>
                  <p className="text-xs text-gray-400 mt-0.5">{a.location} В· {a.assignedTo !== "вЂ”" ? a.assignedTo : "Р‘РµР· РЅР°Р·РЅР°С‡РµРЅРёРµ"}</p>
                </div>
                <span className={`hidden sm:inline-flex items-center gap-1 px-2 py-0.5 rounded-full text-xs ${catColor}`}>
                  {a.category}
                </span>
                <span className={`flex items-center gap-1 px-2 py-0.5 rounded-full text-xs ${s.bg} ${s.color}`}>
                  <SIcon className="size-3" />{s.label}
                </span>
                <span className="hidden lg:block text-xs text-gray-400">{a.value.toLocaleString("bg-BG")} Р»РІ</span>
                <button className="size-8 flex items-center justify-center rounded-lg text-gray-300 hover:bg-gray-100 hover:text-gray-500 transition-all opacity-0 group-hover:opacity-100">
                  <MoreHorizontal className="size-4" />
                </button>
              </div>
            );
          })}
          {shown.length === 0 && (
            <div className="text-center py-10 text-sm text-gray-400">РќСЏРјР° РЅР°РјРµСЂРµРЅРё Р°РєС‚РёРІРё</div>
          )}
        </div>
      </div>
    </div>
  );
}



// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ
// FILE: src/app/pages/pro/ProInquiriesPage.tsx
// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ

import { useState } from "react";
import {
  Plus, Search, MessageSquare, Clock, CheckCircle2,
  AlertCircle, Star, ChevronRight, Send, User,
  Phone, Mail, MapPin, CalendarDays, Euro,
} from "lucide-react";

type InqStatus = "new" | "in_progress" | "quoted" | "won" | "lost";

interface Inquiry {
  id: string;
  client: string;
  phone: string;
  email: string;
  location: string;
  description: string;
  type: string;
  budget: string;
  date: string;
  status: InqStatus;
  priority: "high" | "medium" | "low";
}

const INQUIRIES: Inquiry[] = [
  { id:"1", client:"РќРёРєРѕР»Р°Р№ РўРѕРґРѕСЂРѕРІ",  phone:"0887 123 456", email:"niki@mail.bg",    location:"РєРІ. Р‘РѕСЂРѕРІРѕ, РЎРѕС„РёСЏ",     description:"РџСЉР»РµРЅ СЂРµРјРѕРЅС‚ 90РєРІ. Р°РїР°СЂС‚Р°РјРµРЅС‚ вЂ” СЃР°РЅРёС‚Р°СЂРµРЅ + РјР°Р·РёР»РєРё + С‚РµСЂР°РєРѕС‚",      type:"Р РµРјРѕРЅС‚",         budget:"15-20Рє Р»РІ",  date:"04 Р°РїСЂ 2026", status:"new",        priority:"high"   },
  { id:"2", client:"РђРЅРЅР° РЎС‚РѕРёР»РѕРІР°",    phone:"0896 234 567", email:"anna.s@abv.bg",  location:"СѓР». РҐР°РЅ РђСЃРїР°СЂСѓС…, РџР»РѕРІРґРёРІ",description:"РР·РіСЂР°Р¶РґР°РЅРµ РЅР° РЅР°РІРµСЃ 30РєРІ. + Р±РµС‚РѕРЅРЅР° РЅР°СЃС‚РёР»РєР° РІ РґРІРѕСЂР°",               type:"РќРѕРІРѕ СЃС‚СЂРѕРёС‚РµР»СЃС‚РІРѕ",budget:"8-12Рє Р»РІ", date:"03 Р°РїСЂ 2026", status:"in_progress",priority:"medium" },
  { id:"3", client:"Р’РёРєС‚РѕСЂ РњР°СЂРёРЅРѕРІ",   phone:"0878 345 678", email:"v.marinov@bg.bg",location:"Р’Р°СЂРЅР°, РєРІ. Р§Р°Р№РєР°",        description:"РҐРёРґСЂРѕРёР·РѕР»Р°С†РёСЏ С‚РµСЂР°СЃР° + С‚РѕРїР»РѕРёР·РѕР»Р°С†РёСЏ С„Р°СЃР°РґР°",                       type:"РР·РѕР»Р°С†РёСЏ",       budget:"5-8Рє Р»РІ",   date:"02 Р°РїСЂ 2026", status:"quoted",     priority:"medium" },
  { id:"4", client:"РљСЂР°СЃРёРјРёСЂР° РРІР°РЅРѕРІР°",phone:"0886 456 789", email:"kr.iv@gmail.com",location:"Р‘СѓСЂРіР°СЃ, РєРІ. РњРµРґРµРЅ СЂСѓРґРЅРёРє",description:"РЎС‚СЂРѕРµР¶ РЅР° РіР°СЂР°Р¶ 25РєРІ. СЃ С‚Р°РІР°РЅ Рё РІСЂР°С‚Р°",                             type:"РќРѕРІРѕ СЃС‚СЂРѕРёС‚РµР»СЃС‚РІРѕ",budget:"12Рє Р»РІ",   date:"01 Р°РїСЂ 2026", status:"won",        priority:"high"   },
  { id:"5", client:"РњРµС‚РѕРґРё РљР°СЂР°РјС„РёР»РѕРІ",phone:"0877 567 890", email:"metodi@firma.bg",location:"РЎС‚Р°СЂР° Р—Р°РіРѕСЂР°",            description:"РћС„РёСЃ СЂРµРјРѕРЅС‚ 200РєРІ. вЂ” РїРѕРґРѕРІРё РїРѕРєСЂРёС‚РёСЏ, РіРёРїСЃРѕРєР°СЂС‚РѕРЅ, Р±РѕСЏРґРёСЃРІР°РЅРµ",     type:"Р РµРјРѕРЅС‚",         budget:"30Рє Р»РІ",    date:"30 РјР°СЂС‚ 2026",status:"in_progress",priority:"high"   },
  { id:"6", client:"Р”РёР°РЅР° РџРµС‚РєРѕРІР°",    phone:"0895 678 901", email:"diana.p@mail.bg",location:"Р СѓСЃРµ",                   description:"РЎР°РЅРёСЂР°РЅРµ РЅР° Р¶РёР»РёС‰РµРЅ Р±Р»РѕРє 8 РµС‚. вЂ” С‚РѕРїР»РѕРёР·РѕР»Р°С†РёСЏ + РјР°Р·РёР»РєР° + Р±РѕСЏ",    type:"РЎР°РЅРёСЂР°РЅРµ",       budget:"80Рє Р»РІ",    date:"28 РјР°СЂС‚ 2026",status:"quoted",     priority:"high"   },
  { id:"7", client:"РЎРїР°СЃ РњРёРЅРєРѕРІ",      phone:"0888 789 012", email:"spas.m@abv.bg",  location:"РџР»РµРІРµРЅ",                 description:"РњРѕРЅС‚Р°Р¶ РЅР° РџР’Р¦ РґРѕРіСЂР°РјР° + СЂРѕР»РµС‚РЅРё С‰РѕСЂРё вЂ” 12 РїСЂРѕР·РѕСЂРµС†Р°",               type:"Р”РѕРіСЂР°РјР°",        budget:"4Рє Р»РІ",     date:"25 РјР°СЂС‚ 2026",status:"lost",       priority:"low"    },
];

const STATUS_CFG: Record<InqStatus, { label: string; color: string; bg: string; border: string; icon: typeof Clock }> = {
  new:         { label:"РќРѕРІРѕ",       color:"text-blue-700",    bg:"bg-blue-50",    border:"border-blue-200",    icon: MessageSquare },
  in_progress: { label:"Р’ СЂР°Р±РѕС‚Р°",   color:"text-amber-700",   bg:"bg-amber-50",   border:"border-amber-200",   icon: Clock },
  quoted:      { label:"РР·РїСЂР°С‚РµРЅР° РѕС„РµСЂС‚Р°",color:"text-violet-700",bg:"bg-violet-50",border:"border-violet-200", icon: Send },
  won:         { label:"РЎРїРµС‡РµР»РµРЅРѕ",  color:"text-emerald-700", bg:"bg-emerald-50", border:"border-emerald-200", icon: CheckCircle2 },
  lost:        { label:"РР·РіСѓР±РµРЅРѕ",   color:"text-gray-500",    bg:"bg-gray-100",   border:"border-gray-200",    icon: AlertCircle },
};

const PRIO_CFG = {
  high:   { label:"Р’РёСЃРѕРє",   dot:"bg-red-500"    },
  medium: { label:"РЎСЂРµРґРµРЅ",  dot:"bg-amber-500"  },
  low:    { label:"РќРёСЃСЉРє",   dot:"bg-gray-400"   },
};

export function ProInquiriesPage() {
  const [q, setQ] = useState("");
  const [filter, setFilter] = useState<string>("all");
  const [selected, setSelected] = useState<Inquiry | null>(null);

  const shown = INQUIRIES.filter(i => {
    const mQ = i.client.toLowerCase().includes(q.toLowerCase()) || i.location.toLowerCase().includes(q.toLowerCase());
    const mF = filter === "all" || i.status === filter;
    return mQ && mF;
  });

  return (
    <div className="p-5 lg:p-7 space-y-5">
      {/* Header */}
      <div className="flex flex-col sm:flex-row sm:items-center justify-between gap-3">
        <div>
          <h1 className="text-xl text-gray-800">Р—Р°РїРёС‚РІР°РЅРёСЏ</h1>
          <p className="text-sm text-gray-500 mt-0.5">{INQUIRIES.filter(i=>i.status==="new").length} РЅРѕРІРё В· {INQUIRIES.length} РѕР±С‰Рѕ</p>
        </div>
        <button className="flex items-center gap-2 px-4 py-2.5 rounded-xl bg-gradient-to-r from-blue-600 to-teal-600 text-white text-sm hover:from-blue-700 hover:to-teal-700 shadow-md shadow-blue-200 transition-all active:scale-95 self-start sm:self-auto">
          <Plus className="size-4" />
          РќРѕРІРѕ Р·Р°РїРёС‚РІР°РЅРµ
        </button>
      </div>

      {/* Status bar */}
      <div className="grid grid-cols-2 sm:grid-cols-5 gap-3">
        {(Object.entries(STATUS_CFG) as [InqStatus, typeof STATUS_CFG[InqStatus]][]).map(([k, v]) => {
          const cnt = INQUIRIES.filter(i=>i.status===k).length;
          return (
            <button key={k} onClick={()=>setFilter(filter===k?"all":k)}
              className={`p-3 rounded-xl border transition-all text-left ${filter===k ? `${v.border} ${v.bg}` : "bg-white border-gray-100 hover:bg-gray-50"}`}>
              <p className={`text-lg ${v.color}`}>{cnt}</p>
              <p className="text-xs text-gray-500 mt-0.5">{v.label}</p>
            </button>
          );
        })}
      </div>

      {/* Search */}
      <div className="relative max-w-xs">
        <Search className="absolute left-3 top-1/2 -translate-y-1/2 size-3.5 text-gray-400 pointer-events-none" />
        <input value={q} onChange={e=>setQ(e.target.value)} placeholder="РўСЉСЂСЃРё РєР»РёРµРЅС‚ / Р»РѕРєР°С†РёСЏ..." className="pl-8 pr-3 py-2 text-xs border border-gray-200 rounded-xl focus:outline-none focus:ring-2 focus:ring-blue-500/20 focus:border-blue-400 bg-white w-full" />
      </div>

      <div className="flex flex-col lg:flex-row gap-4">
        {/* List */}
        <div className="flex-1 space-y-2">
          {shown.map(inq => {
            const s = STATUS_CFG[inq.status];
            const SIcon = s.icon;
            const p = PRIO_CFG[inq.priority];
            const isSelected = selected?.id === inq.id;
            return (
              <div key={inq.id} onClick={() => setSelected(isSelected ? null : inq)}
                className={`bg-white rounded-2xl border p-4 cursor-pointer hover:shadow-sm transition-all ${isSelected ? "border-blue-300 ring-1 ring-blue-200" : "border-gray-100"}`}>
                <div className="flex items-start gap-3">
                  <div className="size-9 rounded-xl bg-blue-50 flex items-center justify-center flex-shrink-0">
                    <User className="size-4 text-blue-600" />
                  </div>
                  <div className="flex-1 min-w-0">
                    <div className="flex items-center gap-2 flex-wrap">
                      <p className="text-sm text-gray-800">{inq.client}</p>
                      <span className={`flex items-center gap-1 px-2 py-0.5 rounded-full text-xs ${s.bg} ${s.color}`}>
                        <SIcon className="size-3" />{s.label}
                      </span>
                      <div className="flex items-center gap-1">
                        <span className={`size-1.5 rounded-full ${p.dot}`} />
                        <span className="text-xs text-gray-400">{p.label} РїСЂРёРѕСЂРёС‚РµС‚</span>
                      </div>
                    </div>
                    <p className="text-xs text-gray-500 mt-1 line-clamp-2">{inq.description}</p>
                    <div className="flex items-center gap-3 mt-2 flex-wrap">
                      <span className="flex items-center gap-1 text-xs text-gray-400"><MapPin className="size-3" />{inq.location}</span>
                      <span className="flex items-center gap-1 text-xs text-gray-400"><Euro className="size-3" />{inq.budget}</span>
                      <span className="flex items-center gap-1 text-xs text-gray-400"><CalendarDays className="size-3" />{inq.date}</span>
                    </div>
                  </div>
                  <ChevronRight className={`size-4 text-gray-300 flex-shrink-0 transition-transform mt-1 ${isSelected ? "rotate-90 text-blue-400" : ""}`} />
                </div>

                {/* Expanded detail */}
                {isSelected && (
                  <div className="mt-4 pt-4 border-t border-gray-100 grid grid-cols-1 sm:grid-cols-2 gap-3">
                    <div className="space-y-2">
                      <div className="flex items-center gap-2 text-xs text-gray-600"><Phone className="size-3.5 text-gray-400" />{inq.phone}</div>
                      <div className="flex items-center gap-2 text-xs text-gray-600"><Mail className="size-3.5 text-gray-400" />{inq.email}</div>
                    </div>
                    <div className="flex items-center gap-2">
                      <button className="flex-1 py-2 rounded-xl bg-gradient-to-r from-blue-600 to-teal-600 text-white text-xs hover:from-blue-700 hover:to-teal-700 transition-all">
                        РР·РїСЂР°С‚Рё РѕС„РµСЂС‚Р°
                      </button>
                      <button className="flex-1 py-2 rounded-xl border border-gray-200 text-gray-600 text-xs hover:bg-gray-50 transition-all">
                        AI РѕС†РµРЅРєР°
                      </button>
                    </div>
                  </div>
                )}
              </div>
            );
          })}
          {shown.length === 0 && (
            <div className="text-center py-10 text-sm text-gray-400">РќСЏРјР° РЅР°РјРµСЂРµРЅРё Р·Р°РїРёС‚РІР°РЅРёСЏ</div>
          )}
        </div>
      </div>
    </div>
  );
}



// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ
// FILE: src/app/pages/pro/ProMessagesPage.tsx
// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ

import { useState, useRef, useEffect } from "react";
import {
  Send, Search, Plus, Phone, Video, MoreHorizontal,
  CheckCheck, Check, Paperclip, Smile,
} from "lucide-react";

interface Message {
  id: string;
  text: string;
  time: string;
  mine: boolean;
  read: boolean;
}

interface Conversation {
  id: string;
  name: string;
  role: string;
  avatar: string;
  gradient: string;
  lastMsg: string;
  lastTime: string;
  unread: number;
  online: boolean;
  messages: Message[];
}

const CONVERSATIONS: Conversation[] = [
  {
    id:"1", name:"РРІР°РЅ Р”РёРјРёС‚СЂРѕРІ", role:"РџСЂРѕСЂР°Р± вЂ” Р’РёС‚РѕС€Р° 24", avatar:"РР”",
    gradient:"from-blue-500 to-violet-600",
    lastMsg:"Р¦РёРјРµРЅС‚Р° РїСЂРёСЃС‚РёРіРЅР°. Р—Р°РїРѕС‡РІР°РјРµ СѓС‚СЂРµ.", lastTime:"14:32", unread:2, online:true,
    messages:[
      { id:"m1", text:"РљР°Рє РІСЉСЂРІСЏС‚ РЅРµС‰Р°С‚Р° РЅР° Р’РёС‚РѕС€Р°?", time:"13:10", mine:true, read:true },
      { id:"m2", text:"Р”РѕР±СЂРµ. Р—РёРґР°СЂРёС‚Рµ СЃР° РЅР°РїСЂРµРґ СЃ plan-Р°.", time:"13:15", mine:false, read:true },
      { id:"m3", text:"Р¦РёРјРµРЅС‚Р° С‰Рµ РґРѕР№РґРµ Р»Рё РґРЅРµСЃ?", time:"13:20", mine:true, read:true },
      { id:"m4", text:"Р¦РёРјРµРЅС‚Р° РїСЂРёСЃС‚РёРіРЅР°. Р—Р°РїРѕС‡РІР°РјРµ СѓС‚СЂРµ.", time:"14:32", mine:false, read:false },
      { id:"m5", text:"РРјР°РјРµ РЅСѓР¶РґР° РѕС‚ РѕС‰Рµ 20 С‡СѓРІР°Р»Р°.", time:"14:33", mine:false, read:false },
    ]
  },
  {
    id:"2", name:"РњР°СЂРёСЏ РРІР°РЅРѕРІР°", role:"РљР»РёРµРЅС‚ вЂ” Р РµРјРѕРЅС‚ Р°РїР°СЂС‚Р°РјРµРЅС‚", avatar:"РњР",
    gradient:"from-pink-500 to-rose-600",
    lastMsg:"РљРѕРіР° С‰Рµ Р±СЉРґРµС‚Рµ РіРѕС‚РѕРІРё СЃ Р±Р°РЅСЏС‚Р°?", lastTime:"11:05", unread:1, online:true,
    messages:[
      { id:"m1", text:"Р—РґСЂР°РІРµР№С‚Рµ! РљРѕРіР° С‰Рµ Р±СЉРґРµС‚Рµ РіРѕС‚РѕРІРё СЃ Р±Р°РЅСЏС‚Р°?", time:"11:05", mine:false, read:false },
    ]
  },
  {
    id:"3", name:"РџР»Р°РјРµРЅ РўРѕРґРѕСЂРѕРІ", role:"Р—РёРґР°СЂ вЂ” СЃ. Р“РµСЂРјР°РЅ", avatar:"РџРў",
    gradient:"from-emerald-500 to-teal-600",
    lastMsg:"РћРє, С‰Рµ РґРѕР№РґР° РІ 7:30.", lastTime:"Р’С‡РµСЂР°", unread:0, online:false,
    messages:[
      { id:"m1", text:"РЈС‚СЂРµ С‚СЂСЏР±РІР° РґР° СЃРё РІ 7:30 РІ Р“РµСЂРјР°РЅ.", time:"18:00", mine:true, read:true },
      { id:"m2", text:"РћРє, С‰Рµ РґРѕР№РґР° РІ 7:30.", time:"18:22", mine:false, read:true },
    ]
  },
  {
    id:"4", name:"РџРµС‚СЂРѕРІ & РЎРёРЅРѕРІРµ", role:"РљР»РёРµРЅС‚ вЂ” Р’РёР»Р°", avatar:"РџРЎ",
    gradient:"from-amber-500 to-orange-600",
    lastMsg:"РР·РїСЂР°С‚РµС‚Рµ РЅРё РљРЎРЎ Р·Р° СЃР»РµРґРІР°С‰РёСЏ РµС‚Р°Рї.", lastTime:"Р’С‡РµСЂР°", unread:0, online:false,
    messages:[
      { id:"m1", text:"РР·РїСЂР°С‚РµС‚Рµ РЅРё РљРЎРЎ Р·Р° СЃР»РµРґРІР°С‰РёСЏ РµС‚Р°Рї.", time:"16:00", mine:false, read:true },
    ]
  },
  {
    id:"5", name:"Tech Soft OOD", role:"РљР»РёРµРЅС‚ вЂ” РћС„РёСЃ СЂРµРјРѕРЅС‚", avatar:"РўРЎ",
    gradient:"from-violet-500 to-indigo-600",
    lastMsg:"Р‘Р»Р°РіРѕРґР°СЂРёРј Р·Р° РѕС„РµСЂС‚Р°С‚Р°!", lastTime:"28 РјР°СЂС‚", unread:0, online:false,
    messages:[
      { id:"m1", text:"Р‘Р»Р°РіРѕРґР°СЂРёРј Р·Р° РѕС„РµСЂС‚Р°С‚Р°! Р©Рµ СЃРµ СЃРІСЉСЂР¶РµРј С‚Р°Р·Рё СЃРµРґРјРёС†Р°.", time:"10:00", mine:false, read:true },
    ]
  },
];

export function ProMessagesPage() {
  const [convs, setConvs] = useState(CONVERSATIONS);
  const [activeId, setActiveId] = useState("1");
  const [q, setQ] = useState("");
  const [input, setInput] = useState("");
  const messagesEndRef = useRef<HTMLDivElement>(null);

  const active = convs.find(c => c.id === activeId)!;

  const filtered = convs.filter(c =>
    c.name.toLowerCase().includes(q.toLowerCase()) ||
    c.role.toLowerCase().includes(q.toLowerCase())
  );

  const selectConv = (id: string) => {
    setActiveId(id);
    setConvs(prev => prev.map(c => c.id === id
      ? { ...c, unread: 0, messages: c.messages.map(m => ({ ...m, read: true })) }
      : c
    ));
  };

  const sendMessage = () => {
    if (!input.trim()) return;
    const newMsg: Message = {
      id: `m${Date.now()}`,
      text: input.trim(),
      time: new Date().toLocaleTimeString("bg-BG", { hour:"2-digit", minute:"2-digit" }),
      mine: true,
      read: false,
    };
    setConvs(prev => prev.map(c => c.id === activeId
      ? { ...c, messages: [...c.messages, newMsg], lastMsg: newMsg.text, lastTime: newMsg.time }
      : c
    ));
    setInput("");
  };

  useEffect(() => {
    messagesEndRef.current?.scrollIntoView({ behavior: "smooth" });
  }, [active?.messages]);

  return (
    <div className="flex h-full">
      {/* Sidebar */}
      <div className="w-72 flex-shrink-0 bg-white border-r border-gray-100 flex flex-col">
        <div className="p-4 border-b border-gray-50">
          <div className="flex items-center justify-between mb-3">
            <p className="text-sm text-gray-700">РЎСЉРѕР±С‰РµРЅРёСЏ</p>
            <button className="size-8 flex items-center justify-center rounded-xl bg-blue-50 text-blue-600 hover:bg-blue-100 transition-colors">
              <Plus className="size-4" />
            </button>
          </div>
          <div className="relative">
            <Search className="absolute left-3 top-1/2 -translate-y-1/2 size-3.5 text-gray-400 pointer-events-none" />
            <input value={q} onChange={e=>setQ(e.target.value)} placeholder="РўСЉСЂСЃРё СЂР°Р·РіРѕРІРѕСЂ..." className="pl-8 pr-3 py-2 text-xs border border-gray-200 rounded-xl focus:outline-none focus:ring-2 focus:ring-blue-500/20 focus:border-blue-400 bg-gray-50 w-full" />
          </div>
        </div>
        <div className="flex-1 overflow-y-auto">
          {filtered.map(c => (
            <button key={c.id} onClick={() => selectConv(c.id)}
              className={`w-full flex items-center gap-3 px-4 py-3 hover:bg-gray-50 transition-colors ${activeId===c.id ? "bg-blue-50/50 border-r-2 border-blue-500" : ""}`}>
              <div className="relative flex-shrink-0">
                <div className={`size-10 rounded-full bg-gradient-to-br ${c.gradient} flex items-center justify-center text-white text-xs`}>
                  {c.avatar}
                </div>
                {c.online && <span className="absolute bottom-0 right-0 size-2.5 rounded-full bg-emerald-500 border-2 border-white" />}
              </div>
              <div className="flex-1 min-w-0 text-left">
                <div className="flex items-center justify-between">
                  <p className={`text-sm truncate ${c.unread > 0 ? "text-gray-900" : "text-gray-700"}`}>{c.name}</p>
                  <span className="text-[10px] text-gray-400 flex-shrink-0 ml-2">{c.lastTime}</span>
                </div>
                <div className="flex items-center justify-between mt-0.5">
                  <p className={`text-xs truncate pr-2 ${c.unread > 0 ? "text-gray-600" : "text-gray-400"}`}>{c.lastMsg}</p>
                  {c.unread > 0 && (
                    <span className="size-5 rounded-full bg-blue-600 text-white text-[10px] flex items-center justify-center flex-shrink-0">
                      {c.unread}
                    </span>
                  )}
                </div>
              </div>
            </button>
          ))}
        </div>
      </div>

      {/* Chat window */}
      <div className="flex-1 flex flex-col min-w-0 bg-gray-50">
        {/* Chat header */}
        <div className="h-16 bg-white border-b border-gray-100 flex items-center px-5 gap-3 flex-shrink-0">
          <div className="relative flex-shrink-0">
            <div className={`size-9 rounded-full bg-gradient-to-br ${active.gradient} flex items-center justify-center text-white text-xs`}>
              {active.avatar}
            </div>
            {active.online && <span className="absolute bottom-0 right-0 size-2 rounded-full bg-emerald-500 border-2 border-white" />}
          </div>
          <div>
            <p className="text-sm text-gray-800">{active.name}</p>
            <p className="text-xs text-gray-400">{active.online ? "РћРЅР»Р°Р№РЅ" : "РћС„Р»Р°Р№РЅ"} В· {active.role}</p>
          </div>
          <div className="flex-1" />
          <button className="size-9 flex items-center justify-center rounded-xl text-gray-400 hover:bg-gray-100 transition-colors"><Phone className="size-4" /></button>
          <button className="size-9 flex items-center justify-center rounded-xl text-gray-400 hover:bg-gray-100 transition-colors"><Video className="size-4" /></button>
          <button className="size-9 flex items-center justify-center rounded-xl text-gray-400 hover:bg-gray-100 transition-colors"><MoreHorizontal className="size-4" /></button>
        </div>

        {/* Messages */}
        <div className="flex-1 overflow-y-auto px-5 py-4 space-y-3">
          {active.messages.map(msg => (
            <div key={msg.id} className={`flex ${msg.mine ? "justify-end" : "justify-start"}`}>
              <div className={`max-w-xs lg:max-w-md px-4 py-2.5 rounded-2xl ${msg.mine
                ? "bg-gradient-to-br from-blue-600 to-teal-600 text-white rounded-br-sm"
                : "bg-white text-gray-700 rounded-bl-sm shadow-sm border border-gray-100"
              }`}>
                <p className="text-sm leading-relaxed">{msg.text}</p>
                <div className={`flex items-center justify-end gap-1 mt-1 ${msg.mine ? "text-blue-200" : "text-gray-400"}`}>
                  <span className="text-[10px]">{msg.time}</span>
                  {msg.mine && (msg.read
                    ? <CheckCheck className="size-3" />
                    : <Check className="size-3" />
                  )}
                </div>
              </div>
            </div>
          ))}
          <div ref={messagesEndRef} />
        </div>

        {/* Input */}
        <div className="px-5 py-4 bg-white border-t border-gray-100">
          <div className="flex items-center gap-3 bg-gray-50 rounded-2xl border border-gray-200 px-4 py-2 focus-within:ring-2 focus-within:ring-blue-500/20 focus-within:border-blue-400 transition-all">
            <button className="size-7 flex items-center justify-center text-gray-400 hover:text-gray-600 transition-colors flex-shrink-0">
              <Paperclip className="size-4" />
            </button>
            <input
              value={input}
              onChange={e => setInput(e.target.value)}
              onKeyDown={e => e.key === "Enter" && !e.shiftKey && sendMessage()}
              placeholder="РќР°РїРёС€Рё СЃСЉРѕР±С‰РµРЅРёРµ..."
              className="flex-1 bg-transparent text-sm text-gray-700 placeholder-gray-400 focus:outline-none"
            />
            <button className="size-7 flex items-center justify-center text-gray-400 hover:text-gray-600 transition-colors flex-shrink-0">
              <Smile className="size-4" />
            </button>
            <button onClick={sendMessage} className="size-8 flex items-center justify-center rounded-xl bg-gradient-to-br from-blue-600 to-teal-600 text-white hover:from-blue-700 hover:to-teal-700 transition-all active:scale-95 flex-shrink-0 shadow-sm">
              <Send className="size-3.5" />
            </button>
          </div>
        </div>
      </div>
    </div>
  );
}



// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ
// FILE: src/app/pages/pro/ProTeamPage.tsx
// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ

import {
  Users, Phone, Mail, Star, CheckCircle2, Clock,
  Plus, MoreHorizontal, Zap,
} from "lucide-react";

const TEAM = [
  { id: 1, name: "Р“РµРѕСЂРіРё РЎС‚РѕРµРІ",     role: "Р‘СЂРёРіР°РґРёСЂ",           initials: "Р“РЎ", color: "from-blue-500 to-teal-500",    status: "active", projects: 3, rating: 4.9, phone: "+359 87 111 2233", email: "g.stoev@skstroy.bg", tasks: 7 },
  { id: 2, name: "РџРµС‚СЉСЂ Р”РёРјРёС‚СЂРѕРІ",   role: "РњР°Р№СЃС‚РѕСЂ вЂ” С‚РµСЂР°РєРѕС‚",  initials: "РџР”", color: "from-violet-500 to-blue-500",  status: "active", projects: 2, rating: 4.7, phone: "+359 88 234 5678", email: "p.dimitrov@skstroy.bg", tasks: 5 },
  { id: 3, name: "РњР°СЂС‚РёРЅ РљРѕР»РµРІ",     role: "Р•Р». РёРЅСЃС‚Р°Р»Р°С†РёРё",     initials: "РњРљ", color: "from-emerald-500 to-teal-500", status: "active", projects: 2, rating: 4.8, phone: "+359 89 345 6789", email: "m.kolev@skstroy.bg", tasks: 4 },
  { id: 4, name: "РЎС‚РµС„Р°РЅ РўСЂРёС„РѕРЅРѕРІ",  role: "РћР±С‰ СЂР°Р±РѕС‚РЅРёРє",        initials: "РЎРў", color: "from-amber-500 to-orange-500", status: "away",   projects: 1, rating: 4.5, phone: "+359 87 456 7890", email: "s.trifonov@skstroy.bg", tasks: 3 },
  { id: 5, name: "РРІР°РЅ Р’Р°СЃРёР»РµРІ",     role: "РњР°Р№СЃС‚РѕСЂ вЂ” РјР°Р·РёР»РєРё",  initials: "РР’", color: "from-rose-500 to-pink-500",    status: "active", projects: 2, rating: 4.6, phone: "+359 88 567 8901", email: "i.vasilev@skstroy.bg", tasks: 6 },
];

const TASKS = [
  { who: "Р“РЎ", task: "РРЅСЃРїРµРєС†РёСЏ вЂ” Р’РёС‚РѕС€Р° 24", time: "09:00", done: true },
  { who: "РџР”", task: "РўРµСЂР°РєРѕС‚ С…РѕР» вЂ” РћРїСЉР»С‡РµРЅСЃРєР° 44", time: "10:30", done: false },
  { who: "РњРљ", task: "Р•Р». С‚Р°Р±Р»o вЂ” Р“РµСЂРјР°РЅ", time: "08:00", done: true },
  { who: "РР’", task: "РњР°Р·РёР»РєР° РІС…РѕРґРЅРѕ вЂ” Р‘РѕС‚РµРІ", time: "13:00", done: false },
  { who: "Р“РЎ", task: "РЎСЂРµС‰Р° РєР»РёРµРЅС‚ РњР°СЂРёСЏ РРІР°РЅРѕРІР°", time: "16:00", done: false },
];

function Avatar({ initials, color }: { initials: string; color: string }) {
  return (
    <div className={`size-10 rounded-full bg-gradient-to-br ${color} flex items-center justify-center text-white text-sm flex-shrink-0`}>
      {initials}
    </div>
  );
}

export function ProTeamPage() {
  return (
    <div className="p-5 lg:p-7 space-y-6">
      {/* Header */}
      <div className="flex flex-col sm:flex-row sm:items-center justify-between gap-3">
        <div>
          <h1 className="text-xl text-gray-800">Р•РєРёРї</h1>
          <p className="text-sm text-gray-500 mt-0.5">{TEAM.length} С‡Р»РµРЅР° В· 3 РЅР° С‚РµСЂРµРЅ РґРЅРµСЃ</p>
        </div>
        <button className="flex items-center gap-2 px-4 py-2.5 rounded-xl bg-gradient-to-r from-blue-600 to-teal-600 text-white text-sm hover:from-blue-700 hover:to-teal-700 shadow-md shadow-blue-200 transition-all active:scale-95 self-start sm:self-auto">
          <Plus className="size-4" />
          Р”РѕР±Р°РІРё С‡Р»РµРЅ
        </button>
      </div>

      <div className="grid grid-cols-1 lg:grid-cols-3 gap-5">
        {/* Team cards */}
        <div className="lg:col-span-2 space-y-3">
          {TEAM.map(m => (
            <div key={m.id} className="bg-white rounded-2xl border border-gray-100 p-4 hover:shadow-sm transition-all">
              <div className="flex items-start gap-4">
                <Avatar initials={m.initials} color={m.color} />
                <div className="flex-1 min-w-0">
                  <div className="flex items-center gap-2">
                    <p className="text-sm text-gray-800">{m.name}</p>
                    <span className={`size-2 rounded-full ${m.status === "active" ? "bg-emerald-500" : "bg-amber-400"}`} />
                  </div>
                  <p className="text-xs text-gray-500">{m.role}</p>
                  <div className="flex flex-wrap gap-3 mt-2">
                    <span className="flex items-center gap-1 text-xs text-gray-500">
                      <Star className="size-3 text-amber-400" />
                      {m.rating}
                    </span>
                    <span className="flex items-center gap-1 text-xs text-gray-500">
                      <CheckCircle2 className="size-3 text-blue-400" />
                      {m.projects} РїСЂРѕРµРєС‚Р°
                    </span>
                    <span className="flex items-center gap-1 text-xs text-gray-500">
                      <Zap className="size-3 text-teal-400" />
                      {m.tasks} Р·Р°РґР°С‡Рё
                    </span>
                  </div>
                </div>
                <div className="flex flex-col items-end gap-2">
                  <button className="size-7 flex items-center justify-center rounded-lg text-gray-300 hover:bg-gray-100 hover:text-gray-600 transition-all">
                    <MoreHorizontal className="size-4" />
                  </button>
                  <div className="flex gap-1.5">
                    <a href={`tel:${m.phone}`} className="size-7 flex items-center justify-center rounded-lg border border-gray-100 text-gray-400 hover:bg-blue-50 hover:text-blue-600 hover:border-blue-100 transition-all">
                      <Phone className="size-3.5" />
                    </a>
                    <a href={`mailto:${m.email}`} className="size-7 flex items-center justify-center rounded-lg border border-gray-100 text-gray-400 hover:bg-teal-50 hover:text-teal-600 hover:border-teal-100 transition-all">
                      <Mail className="size-3.5" />
                    </a>
                  </div>
                </div>
              </div>
            </div>
          ))}
        </div>

        {/* Today's tasks */}
        <div className="bg-white rounded-2xl border border-gray-100 p-5">
          <div className="flex items-center justify-between mb-4">
            <p className="text-sm text-gray-800">Р—Р°РґР°С‡Рё РґРЅРµСЃ</p>
            <Clock className="size-4 text-gray-400" />
          </div>
          <div className="space-y-3">
            {TASKS.map((t, i) => (
              <div key={i} className={`flex items-center gap-3 p-2.5 rounded-xl ${t.done ? "bg-gray-50" : "bg-blue-50/50"}`}>
                <div className="size-7 rounded-full bg-gradient-to-br from-blue-400 to-teal-400 flex items-center justify-center text-white text-[10px] flex-shrink-0">
                  {t.who}
                </div>
                <div className="flex-1 min-w-0">
                  <p className={`text-xs ${t.done ? "text-gray-400 line-through" : "text-gray-700"} truncate`}>{t.task}</p>
                  <p className="text-[10px] text-gray-400">{t.time}</p>
                </div>
                {t.done && <CheckCircle2 className="size-4 text-emerald-400 flex-shrink-0" />}
              </div>
            ))}
          </div>
          <button className="w-full mt-3 flex items-center justify-center gap-1.5 py-2 rounded-xl border border-dashed border-gray-200 text-xs text-gray-400 hover:border-blue-300 hover:text-blue-600 transition-all">
            <Plus className="size-3" />
            Р”РѕР±Р°РІРё Р·Р°РґР°С‡Р°
          </button>
        </div>
      </div>
    </div>
  );
}



// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ
// FILE: src/app/pages/pro/ProAnalyticsPage.tsx
// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ

import {
  TrendingUp, Euro, BarChart3, Users,
  ArrowUpRight, ArrowDownRight, Calendar,
} from "lucide-react";
import {
  AreaChart, Area, BarChart, Bar, XAxis, YAxis,
  CartesianGrid, Tooltip, ResponsiveContainer, PieChart, Pie, Cell,
} from "recharts";

const MONTHLY = [
  { month: "РћРєС‚", revenue: 22000, expenses: 14000 },
  { month: "РќРѕРµ", revenue: 28000, expenses: 16000 },
  { month: "Р”РµРє", revenue: 19000, expenses: 12000 },
  { month: "РЇРЅСѓ", revenue: 31000, expenses: 18000 },
  { month: "Р¤РµРІ", revenue: 35000, expenses: 20000 },
  { month: "РњР°СЂ", revenue: 38450, expenses: 21000 },
];

const PROJECT_TYPES = [
  { name: "Р РµРјРѕРЅС‚", value: 42, color: "#2563EB" },
  { name: "РќРѕРІРѕ СЃС‚СЂ.", value: 28, color: "#0D9488" },
  { name: "Р‘РѕСЏРґРёСЃРІР°РЅРµ", value: 15, color: "#7C3AED" },
  { name: "Р”РѕРІСЉСЂС€РёС‚РµР»РЅРё", value: 10, color: "#D97706" },
  { name: "РЎР°РЅРёСЂР°РЅРµ", value: 5, color: "#DC2626" },
];

const KPIS = [
  { label: "РџСЂРёС…РѕРґРё (РјР°СЂС‚)", value: "38 450 Р»РІ", change: "+12%", up: true, icon: Euro,      color: "text-emerald-600", bg: "bg-emerald-50", border: "border-emerald-100" },
  { label: "Р Р°Р·С…РѕРґРё (РјР°СЂС‚)", value: "21 000 Р»РІ", change: "+5%",  up: false, icon: BarChart3, color: "text-blue-600",    bg: "bg-blue-50",    border: "border-blue-100" },
  { label: "РќРµС‚РЅР° РїРµС‡Р°Р»Р±Р°",  value: "17 450 Р»РІ", change: "+21%", up: true,  icon: TrendingUp,color: "text-teal-600",   bg: "bg-teal-50",    border: "border-teal-100" },
  { label: "РџСЂРѕРµРєС‚Рё",        value: "14",         change: "+3",   up: true,  icon: Calendar,  color: "text-violet-600", bg: "bg-violet-50",  border: "border-violet-100" },
];

const TOP_CLIENTS = [
  { name: "РџРµС‚СЂРѕРІ & РЎРёРЅРѕРІРµ",   revenue: "87 200 Р»РІ", projects: 1, badge: "рџҐ‡" },
  { name: "Tech Soft OOD",     revenue: "24 900 Р»РІ", projects: 1, badge: "рџҐ€" },
  { name: "РњР°СЂРёСЏ РРІР°РЅРѕРІР°",     revenue: "12 400 Р»РІ", projects: 1, badge: "рџҐ‰" },
  { name: "РҐСЂРёСЃС‚Рѕ РЎС‚РѕРµРІ",      revenue: "18 600 Р»РІ", projects: 1, badge: "" },
  { name: "РЎРЅРµР¶Р°РЅР° Р“РµРѕСЂРіРёРµРІР°", revenue: "3 200 Р»РІ",  projects: 1, badge: "" },
];

export function ProAnalyticsPage() {
  return (
    <div className="p-5 lg:p-7 space-y-6">
      {/* Header */}
      <div className="flex items-center justify-between">
        <div>
          <h1 className="text-xl text-gray-800">Р¤РёРЅР°РЅСЃРѕРІРё Р°РЅР°Р»РёР·Рё</h1>
          <p className="text-sm text-gray-500 mt-0.5">РњР°СЂС‚ 2026 В· РЎРљ РЎС‚СЂРѕР№ Р•РћРћР”</p>
        </div>
        <div className="flex items-center gap-2 px-3 py-1.5 rounded-xl border border-gray-200 text-sm text-gray-600">
          <Calendar className="size-4" />
          РњР°СЂС‚ 2026
        </div>
      </div>

      {/* KPIs */}
      <div className="grid grid-cols-2 lg:grid-cols-4 gap-4">
        {KPIS.map(k => {
          const Icon = k.icon;
          return (
            <div key={k.label} className={`bg-white rounded-2xl border ${k.border} p-4 hover:shadow-sm transition-all`}>
              <div className="flex items-center justify-between mb-3">
                <div className={`size-9 rounded-xl ${k.bg} flex items-center justify-center`}>
                  <Icon className={`size-4 ${k.color}`} />
                </div>
                <span className={`flex items-center gap-0.5 text-xs px-2 py-0.5 rounded-full ${k.up ? "bg-emerald-50 text-emerald-600" : "bg-red-50 text-red-600"}`}>
                  {k.up ? <ArrowUpRight className="size-3" /> : <ArrowDownRight className="size-3" />}
                  {k.change}
                </span>
              </div>
              <p className="text-xl text-gray-800">{k.value}</p>
              <p className="text-xs text-gray-500 mt-0.5">{k.label}</p>
            </div>
          );
        })}
      </div>

      {/* Charts row */}
      <div className="grid grid-cols-1 lg:grid-cols-3 gap-5">
        {/* Revenue chart */}
        <div className="lg:col-span-2 bg-white rounded-2xl border border-gray-100 p-5">
          <p className="text-sm text-gray-800 mb-1">РџСЂРёС…РѕРґРё vs Р Р°Р·С…РѕРґРё (6 РјРµСЃРµС†Р°)</p>
          <p className="text-xs text-gray-400 mb-4">РїРѕСЃР»РµРґРЅРёС‚Рµ 6 РјРµСЃРµС†Р°</p>
          <ResponsiveContainer width="100%" height={200}>
            <AreaChart data={MONTHLY} margin={{ top: 5, right: 5, bottom: 0, left: 0 }}>
              <defs>
                <linearGradient id="revGrad" x1="0" y1="0" x2="0" y2="1">
                  <stop offset="5%" stopColor="#2563EB" stopOpacity={0.15} />
                  <stop offset="95%" stopColor="#2563EB" stopOpacity={0} />
                </linearGradient>
                <linearGradient id="expGrad" x1="0" y1="0" x2="0" y2="1">
                  <stop offset="5%" stopColor="#0D9488" stopOpacity={0.12} />
                  <stop offset="95%" stopColor="#0D9488" stopOpacity={0} />
                </linearGradient>
              </defs>
              <CartesianGrid strokeDasharray="3 3" stroke="#f0f0f0" />
              <XAxis dataKey="month" tick={{ fontSize: 11, fill: "#9ca3af" }} axisLine={false} tickLine={false} />
              <YAxis tick={{ fontSize: 11, fill: "#9ca3af" }} axisLine={false} tickLine={false} tickFormatter={v => `${(v/1000).toFixed(0)}k`} />
              <Tooltip formatter={(v: number) => `${v.toLocaleString("bg-BG")} Р»РІ`} />
              <Area type="monotone" dataKey="revenue" stroke="#2563EB" strokeWidth={2} fill="url(#revGrad)" name="РџСЂРёС…РѕРґРё" />
              <Area type="monotone" dataKey="expenses" stroke="#0D9488" strokeWidth={2} fill="url(#expGrad)" name="Р Р°Р·С…РѕРґРё" />
            </AreaChart>
          </ResponsiveContainer>
          <div className="flex gap-4 mt-3">
            <div className="flex items-center gap-1.5"><div className="size-2.5 rounded-full bg-blue-600" /><span className="text-xs text-gray-500">РџСЂРёС…РѕРґРё</span></div>
            <div className="flex items-center gap-1.5"><div className="size-2.5 rounded-full bg-teal-600" /><span className="text-xs text-gray-500">Р Р°Р·С…РѕРґРё</span></div>
          </div>
        </div>

        {/* Pie chart */}
        <div className="bg-white rounded-2xl border border-gray-100 p-5">
          <p className="text-sm text-gray-800 mb-4">Р’РёРґРѕРІРµ РїСЂРѕРµРєС‚Рё</p>
          <ResponsiveContainer width="100%" height={150}>
            <PieChart>
              <Pie data={PROJECT_TYPES} cx="50%" cy="50%" innerRadius={45} outerRadius={70} dataKey="value" strokeWidth={2}>
                {PROJECT_TYPES.map((entry, i) => (
                  <Cell key={i} fill={entry.color} />
                ))}
              </Pie>
              <Tooltip formatter={(v: number) => `${v}%`} />
            </PieChart>
          </ResponsiveContainer>
          <div className="space-y-2 mt-2">
            {PROJECT_TYPES.map(t => (
              <div key={t.name} className="flex items-center gap-2">
                <div className="size-2.5 rounded-full flex-shrink-0" style={{ background: t.color }} />
                <span className="text-xs text-gray-600 flex-1">{t.name}</span>
                <span className="text-xs text-gray-400">{t.value}%</span>
              </div>
            ))}
          </div>
        </div>
      </div>

      {/* Top clients */}
      <div className="bg-white rounded-2xl border border-gray-100 p-5">
        <p className="text-sm text-gray-800 mb-4">РўРѕРї РєР»РёРµРЅС‚Рё (РїРѕ СЃС‚РѕР№РЅРѕСЃС‚)</p>
        <div className="space-y-3">
          {TOP_CLIENTS.map((c, i) => (
            <div key={i} className="flex items-center gap-3">
              <span className="text-base w-6 text-center">{c.badge || `${i + 1}`}</span>
              <p className="flex-1 text-sm text-gray-700">{c.name}</p>
              <div className="hidden sm:block w-40">
                <div className="h-1.5 bg-gray-100 rounded-full overflow-hidden">
                  <div
                    className="h-full rounded-full bg-gradient-to-r from-blue-500 to-teal-500"
                    style={{ width: `${100 - i * 18}%` }}
                  />
                </div>
              </div>
              <p className="text-sm text-gray-800 w-28 text-right">{c.revenue}</p>
            </div>
          ))}
        </div>
      </div>
    </div>
  );
}



// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ
// FILE: src/app/pages/pro/ProGooglePage.tsx
// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ

import { useState } from "react";
import {
  Calendar, FileSpreadsheet, HardDrive, Mail, Video,
  CheckCircle2, RefreshCw, Link2, Plus, Clock,
  ChevronRight, ExternalLink, Zap, AlertCircle,
} from "lucide-react";

// в”Ђв”Ђв”Ђ Google service cards в”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђ
const SERVICES = [
  {
    id: "calendar",
    name: "Google РљР°Р»РµРЅРґР°СЂ",
    desc: "РЎРёРЅС…СЂРѕРЅРёР·РёСЂР°Р№ СЃСЂРѕРєРѕРІРµ, СЃСЂРµС‰Рё Рё СЃС‚СЂРѕРёС‚РµР»РЅРё РґРµР№РЅРѕСЃС‚Рё",
    icon: Calendar,
    color: "text-blue-600",
    bg: "bg-blue-50",
    border: "border-blue-100",
    connected: true,
    badge: "РЎРІСЉСЂР·Р°РЅ",
  },
  {
    id: "drive",
    name: "Google Drive",
    desc: "РЎСЉС…СЂР°РЅСЏРІР°Р№ С‡РµСЂС‚РµР¶Рё, РґРѕРіРѕРІРѕСЂРё Рё СЃРЅРёРјРєРё Р°РІС‚РѕРјР°С‚РёС‡РЅРѕ",
    icon: HardDrive,
    color: "text-yellow-600",
    bg: "bg-yellow-50",
    border: "border-yellow-100",
    connected: true,
    badge: "РЎРІСЉСЂР·Р°РЅ",
  },
  {
    id: "sheets",
    name: "Google Sheets",
    desc: "РЎРёРЅС…СЂРѕРЅРёР·РёСЂР°Р№ РљРЎРЎ Рё С„РёРЅР°РЅСЃРѕРІРё РґР°РЅРЅРё РІ СЂРµР°Р»РЅРѕ РІСЂРµРјРµ",
    icon: FileSpreadsheet,
    color: "text-emerald-600",
    bg: "bg-emerald-50",
    border: "border-emerald-100",
    connected: false,
    badge: "РЎРІСЉСЂР¶Рё",
  },
  {
    id: "gmail",
    name: "Gmail",
    desc: "РР·РїСЂР°С‰Р°Р№ РѕС„РµСЂС‚Рё, РґРѕРіРѕРІРѕСЂРё Рё РёР·РІРµСЃС‚РёСЏ РґРёСЂРµРєС‚РЅРѕ",
    icon: Mail,
    color: "text-red-600",
    bg: "bg-red-50",
    border: "border-red-100",
    connected: false,
    badge: "РЎРІСЉСЂР¶Рё",
  },
  {
    id: "meet",
    name: "Google Meet",
    desc: "РћСЂРіР°РЅРёР·РёСЂР°Р№ РІРёРґРµРѕСЃСЂРµС‰Рё СЃ РєР»РёРµРЅС‚Рё Рё РµРєРёРїР°",
    icon: Video,
    color: "text-teal-600",
    bg: "bg-teal-50",
    border: "border-teal-100",
    connected: false,
    badge: "РЎРІСЉСЂР¶Рё",
  },
];

// в”Ђв”Ђв”Ђ Calendar events в”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђ
const EVENTS = [
  { time: "09:00", title: "РРЅСЃРїРµРєС†РёСЏ вЂ” СѓР». Р’РёС‚РѕС€Р° 24",       color: "bg-blue-500",    eta: "Р”РЅРµСЃ" },
  { time: "11:30", title: "РЎСЂРµС‰Р° РєР»РёРµРЅС‚ вЂ” РџРµС‚СЂРѕРІ & РЎРёРЅРѕРІРµ",  color: "bg-violet-500",  eta: "Р”РЅРµСЃ" },
  { time: "14:00", title: "Р”РѕСЃС‚Р°РІРєР° РјР°С‚РµСЂРёР°Р»Рё вЂ” СЃ. Р“РµСЂРјР°РЅ",  color: "bg-amber-500",   eta: "Р”РЅРµСЃ" },
  { time: "09:00", title: "РЎС‚Р°СЂС‚РёСЂР°РЅРµ вЂ” РћРїСЉР»С‡РµРЅСЃРєР° 44",      color: "bg-emerald-500", eta: "РЈС‚СЂРµ" },
  { time: "16:00", title: "РџСЂРµРіР»РµРґ РѕС„РµСЂС‚Р° Tech Soft OOD",    color: "bg-teal-500",    eta: "РЈС‚СЂРµ" },
];

// в”Ђв”Ђв”Ђ Drive files в”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђ
const FILES = [
  { name: "РљРЎРЎ_Р’РёС‚РѕС€Р°_24_v3.xlsx",     size: "48 KB",  date: "03 Р°РїСЂ",  type: "sheet" },
  { name: "Р”РѕРіРѕРІРѕСЂ_РџРµС‚СЂРѕРІ_РЎРёРЅРѕРІРµ.pdf", size: "124 KB", date: "01 Р°РїСЂ",  type: "pdf"   },
  { name: "Р§РµСЂС‚РµР¶Рё_Р“РµСЂРјР°РЅ_Final.zip",  size: "8.4 MB", date: "28 РјР°СЂС‚", type: "zip"   },
  { name: "РЎРЅРёРјРєРё_РїСЂРѕРіСЂРµСЃ_Р‘РѕС‚РµРІ.zip",  size: "22 MB",  date: "25 РјР°СЂС‚", type: "zip"   },
];

const FILE_COLORS: Record<string, string> = {
  sheet: "text-emerald-600",
  pdf:   "text-red-600",
  zip:   "text-amber-600",
};

// в”Ђв”Ђв”Ђ Auto-sync rules в”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђ
const RULES = [
  { label: "РљРЎРЎ в†’ Google Sheets",           active: true  },
  { label: "РќРѕРІ РґРѕРіРѕРІРѕСЂ в†’ Drive РїР°РїРєР°",     active: true  },
  { label: "РЎСЂРѕРє РЅР° РїСЂРѕРµРєС‚ в†’ РљР°Р»РµРЅРґР°СЂ",     active: true  },
  { label: "РћС„РµСЂС‚Р° в†’ Gmail РґРѕ РєР»РёРµРЅС‚Р°",     active: false },
  { label: "Р¤РёРЅР°РЅСЃРѕРІ РѕС‚С‡РµС‚ в†’ Sheets",       active: false },
];

// в”Ђв”Ђв”Ђ Component в”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђ
export function ProGooglePage() {
  const [services, setServices] = useState(SERVICES);
  const [rules, setRules] = useState(RULES);
  const [syncing, setSyncing] = useState(false);

  const toggleService = (id: string) => {
    setServices(prev =>
      prev.map(s => s.id === id ? { ...s, connected: !s.connected, badge: !s.connected ? "РЎРІСЉСЂР·Р°РЅ" : "РЎРІСЉСЂР¶Рё" } : s)
    );
  };

  const toggleRule = (i: number) => {
    setRules(prev => prev.map((r, idx) => idx === i ? { ...r, active: !r.active } : r));
  };

  const handleSync = () => {
    setSyncing(true);
    setTimeout(() => setSyncing(false), 1800);
  };

  return (
    <div className="p-5 lg:p-7 space-y-6">
      {/* Header */}
      <div className="flex flex-col sm:flex-row sm:items-center justify-between gap-3">
        <div>
          <h1 className="text-xl text-gray-800">Google РёРЅС‚РµРіСЂР°С†РёСЏ</h1>
          <p className="text-sm text-gray-500 mt-0.5">РЎРІСЉСЂР¶Рµ TemaDom PRO СЃ Google Workspace</p>
        </div>
        <button
          onClick={handleSync}
          className={`flex items-center gap-2 px-4 py-2.5 rounded-xl text-sm transition-all active:scale-95 self-start sm:self-auto ${
            syncing
              ? "bg-emerald-100 text-emerald-700 border border-emerald-200"
              : "bg-gradient-to-r from-blue-600 to-teal-600 text-white shadow-md shadow-blue-200 hover:from-blue-700 hover:to-teal-700"
          }`}
        >
          <RefreshCw className={`size-4 ${syncing ? "animate-spin" : ""}`} />
          {syncing ? "РЎРёРЅС…СЂРѕРЅРёР·РёСЂР°РЅРµ..." : "РЎРёРЅС…СЂРѕРЅРёР·РёСЂР°Р№"}
        </button>
      </div>

      {/* Services grid */}
      <div className="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-4">
        {services.map(s => {
          const Icon = s.icon;
          return (
            <div key={s.id} className={`bg-white rounded-2xl border ${s.border} p-5 hover:shadow-sm transition-all`}>
              <div className="flex items-start justify-between mb-3">
                <div className={`size-11 rounded-xl ${s.bg} flex items-center justify-center`}>
                  <Icon className={`size-5 ${s.color}`} />
                </div>
                <button
                  onClick={() => toggleService(s.id)}
                  className={`px-3 py-1 rounded-full text-xs transition-all ${
                    s.connected
                      ? "bg-emerald-50 text-emerald-600 border border-emerald-100 hover:bg-red-50 hover:text-red-600 hover:border-red-100"
                      : "bg-blue-600 text-white hover:bg-blue-700"
                  }`}
                >
                  {s.connected
                    ? <span className="flex items-center gap-1"><CheckCircle2 className="size-3" />{s.badge}</span>
                    : <span className="flex items-center gap-1"><Link2 className="size-3" />{s.badge}</span>
                  }
                </button>
              </div>
              <p className="text-sm text-gray-800 mb-1">{s.name}</p>
              <p className="text-xs text-gray-500 leading-relaxed">{s.desc}</p>
              {s.connected && (
                <div className="mt-3 flex items-center gap-1.5">
                  <span className="size-1.5 rounded-full bg-emerald-500 animate-pulse" />
                  <span className="text-xs text-emerald-600">РђРєС‚РёРІРЅР° СЃРёРЅС…СЂРѕРЅРёР·Р°С†РёСЏ</span>
                </div>
              )}
            </div>
          );
        })}
      </div>

      {/* Calendar + Drive preview */}
      <div className="grid grid-cols-1 lg:grid-cols-2 gap-5">

        {/* Calendar events */}
        <div className="bg-white rounded-2xl border border-gray-100 p-5">
          <div className="flex items-center justify-between mb-4">
            <div className="flex items-center gap-2">
              <Calendar className="size-4 text-blue-600" />
              <p className="text-sm text-gray-800">РџСЂРµРґСЃС‚РѕСЏС‰Рё РѕС‚ РљР°Р»РµРЅРґР°СЂ</p>
            </div>
            <button className="text-xs text-blue-600 hover:text-blue-700 flex items-center gap-1">
              РћС‚РІРѕСЂРё <ExternalLink className="size-3" />
            </button>
          </div>
          <div className="space-y-2">
            {EVENTS.map((ev, i) => (
              <div key={i} className="flex items-center gap-3 p-3 rounded-xl hover:bg-gray-50 transition-colors cursor-pointer group">
                <div className={`size-2.5 rounded-full ${ev.color} flex-shrink-0`} />
                <div className="flex-1 min-w-0">
                  <p className="text-sm text-gray-700 truncate">{ev.title}</p>
                  <p className="text-xs text-gray-400">{ev.time}</p>
                </div>
                <span className={`text-xs px-2 py-0.5 rounded-full flex-shrink-0 ${ev.eta === "Р”РЅРµСЃ" ? "bg-blue-50 text-blue-600" : "bg-gray-100 text-gray-500"}`}>
                  {ev.eta}
                </span>
                <ChevronRight className="size-3.5 text-gray-300 group-hover:text-gray-500 transition-colors flex-shrink-0" />
              </div>
            ))}
          </div>
          <button className="w-full mt-3 flex items-center justify-center gap-1.5 py-2 rounded-xl border border-dashed border-gray-200 text-xs text-gray-400 hover:border-blue-300 hover:text-blue-600 transition-all">
            <Plus className="size-3" />
            Р”РѕР±Р°РІРё СЃСЉР±РёС‚РёРµ РІ РљР°Р»РµРЅРґР°СЂ
          </button>
        </div>

        {/* Drive files */}
        <div className="bg-white rounded-2xl border border-gray-100 p-5">
          <div className="flex items-center justify-between mb-4">
            <div className="flex items-center gap-2">
              <HardDrive className="size-4 text-yellow-600" />
              <p className="text-sm text-gray-800">Google Drive вЂ” РїРѕСЃР»РµРґРЅРё С„Р°Р№Р»РѕРІРµ</p>
            </div>
            <button className="text-xs text-blue-600 hover:text-blue-700 flex items-center gap-1">
              РћС‚РІРѕСЂРё <ExternalLink className="size-3" />
            </button>
          </div>
          <div className="space-y-2">
            {FILES.map((f, i) => (
              <div key={i} className="flex items-center gap-3 p-3 rounded-xl hover:bg-gray-50 transition-colors cursor-pointer group">
                <FileSpreadsheet className={`size-5 flex-shrink-0 ${FILE_COLORS[f.type]}`} />
                <div className="flex-1 min-w-0">
                  <p className="text-xs text-gray-700 truncate">{f.name}</p>
                  <p className="text-[10px] text-gray-400">{f.size} В· {f.date}</p>
                </div>
                <ExternalLink className="size-3.5 text-gray-300 group-hover:text-blue-500 transition-colors flex-shrink-0" />
              </div>
            ))}
          </div>
          <button className="w-full mt-3 flex items-center justify-center gap-1.5 py-2 rounded-xl border border-dashed border-gray-200 text-xs text-gray-400 hover:border-yellow-300 hover:text-yellow-600 transition-all">
            <Plus className="size-3" />
            РљР°С‡Рё С„Р°Р№Р» РІ Drive
          </button>
        </div>
      </div>

      {/* Auto-sync rules */}
      <div className="bg-white rounded-2xl border border-gray-100 p-5">
        <div className="flex items-center gap-2 mb-4">
          <Zap className="size-4 text-teal-600" />
          <p className="text-sm text-gray-800">РђРІС‚РѕРјР°С‚РёС‡РЅРё РїСЂР°РІРёР»Р° Р·Р° СЃРёРЅС…СЂРѕРЅРёР·Р°С†РёСЏ</p>
        </div>
        <div className="space-y-3">
          {rules.map((r, i) => (
            <div key={i} className="flex items-center justify-between">
              <div className="flex items-center gap-2.5">
                {r.active
                  ? <CheckCircle2 className="size-4 text-emerald-500 flex-shrink-0" />
                  : <AlertCircle className="size-4 text-gray-300 flex-shrink-0" />
                }
                <p className={`text-sm ${r.active ? "text-gray-700" : "text-gray-400"}`}>{r.label}</p>
              </div>
              <button
                onClick={() => toggleRule(i)}
                className={`relative w-9 h-5 rounded-full transition-colors flex-shrink-0 ${r.active ? "bg-teal-500" : "bg-gray-200"}`}
              >
                <span className={`absolute top-0.5 size-4 rounded-full bg-white shadow transition-transform ${r.active ? "translate-x-4" : "translate-x-0.5"}`} />
              </button>
            </div>
          ))}
        </div>
      </div>
    </div>
  );
}



// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ
// FILE: src/app/pages/pro/ProSettingsPage.tsx
// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ

import { useState } from "react";
import {
  Building2, User, Bell, Shield, CreditCard,
  Globe, Save, Crown, Check,
} from "lucide-react";

const TABS = [
  { id: "firm",    label: "Р¤РёСЂРјР°",      icon: Building2 },
  { id: "profile", label: "РџСЂРѕС„РёР»",     icon: User },
  { id: "notif",   label: "РР·РІРµСЃС‚РёСЏ",   icon: Bell },
  { id: "security",label: "РЎРёРіСѓСЂРЅРѕСЃС‚",  icon: Shield },
  { id: "billing", label: "РђР±РѕРЅР°РјРµРЅС‚",  icon: CreditCard },
];

export function ProSettingsPage() {
  const [tab, setTab] = useState("firm");
  const [saved, setSaved] = useState(false);

  const handleSave = () => {
    setSaved(true);
    setTimeout(() => setSaved(false), 2000);
  };

  return (
    <div className="p-5 lg:p-7 max-w-4xl mx-auto space-y-5">
      <div>
        <h1 className="text-xl text-gray-800">РќР°СЃС‚СЂРѕР№РєРё</h1>
        <p className="text-sm text-gray-500 mt-0.5">РЈРїСЂР°РІР»РµРЅРёРµ РЅР° С„РёСЂРјРµРЅРёСЏ Р°РєР°СѓРЅС‚</p>
      </div>

      <div className="flex gap-5 flex-col lg:flex-row">
        {/* Sidebar tabs */}
        <div className="flex lg:flex-col gap-1 overflow-x-auto lg:overflow-visible lg:w-44 flex-shrink-0">
          {TABS.map(t => {
            const Icon = t.icon;
            return (
              <button
                key={t.id}
                onClick={() => setTab(t.id)}
                className={`flex items-center gap-2.5 px-3 py-2.5 rounded-xl text-sm transition-all whitespace-nowrap ${
                  tab === t.id
                    ? "bg-blue-50 text-blue-700"
                    : "text-gray-600 hover:bg-gray-100"
                }`}
              >
                <Icon className={`size-4 ${tab === t.id ? "text-blue-600" : "text-gray-400"}`} />
                {t.label}
              </button>
            );
          })}
        </div>

        {/* Content */}
        <div className="flex-1 bg-white rounded-2xl border border-gray-100 p-6 space-y-5">
          {tab === "firm" && (
            <>
              <p className="text-sm text-gray-800 border-b border-gray-50 pb-3">Р”Р°РЅРЅРё РЅР° С„РёСЂРјР°С‚Р°</p>
              <div className="grid grid-cols-1 sm:grid-cols-2 gap-4">
                {[
                  { label: "РќР°РёРјРµРЅРѕРІР°РЅРёРµ", val: "РЎРљ РЎС‚СЂРѕР№ Р•РћРћР”" },
                  { label: "Р•РРљ / Р‘СѓР»СЃС‚Р°С‚", val: "206123456" },
                  { label: "РњРћР›", val: "РЎС‚РѕСЏРЅ РљРѕР»РµРІ" },
                  { label: "РўРµР»РµС„РѕРЅ", val: "+359 87 888 9900" },
                  { label: "РРјРµР№Р»", val: "office@skstroy.bg" },
                  { label: "РЈРµР±СЃР°Р№С‚", val: "skstroy.bg" },
                ].map(f => (
                  <div key={f.label}>
                    <label className="text-xs text-gray-500 mb-1 block">{f.label}</label>
                    <input
                      defaultValue={f.val}
                      className="w-full px-3 py-2 rounded-xl border border-gray-200 text-sm text-gray-800 focus:outline-none focus:ring-2 focus:ring-blue-500/20 focus:border-blue-400 transition-all"
                    />
                  </div>
                ))}
              </div>
              <div>
                <label className="text-xs text-gray-500 mb-1 block">РђРґСЂРµСЃ РЅР° СѓРїСЂР°РІР»РµРЅРёРµ</label>
                <input
                  defaultValue="РіСЂ. РЎРѕС„РёСЏ, Р±СѓР». Р’РёС‚РѕС€Р° 45, РµС‚. 3"
                  className="w-full px-3 py-2 rounded-xl border border-gray-200 text-sm text-gray-800 focus:outline-none focus:ring-2 focus:ring-blue-500/20 focus:border-blue-400 transition-all"
                />
              </div>
            </>
          )}

          {tab === "profile" && (
            <>
              <p className="text-sm text-gray-800 border-b border-gray-50 pb-3">Р›РёС‡РµРЅ РїСЂРѕС„РёР»</p>
              <div className="flex items-center gap-4 mb-4">
                <div className="size-16 rounded-full bg-gradient-to-br from-violet-500 to-blue-600 flex items-center justify-center text-white text-xl">
                  РЎРЎ
                </div>
                <div>
                  <p className="text-sm text-gray-800">РЎС‚РѕСЏРЅ РљРѕР»РµРІ</p>
                  <p className="text-xs text-amber-600 flex items-center gap-1"><Crown className="size-3" /> РџСЂРµРјРёСѓРј AI</p>
                  <button className="text-xs text-blue-600 mt-1 hover:underline">РџСЂРѕРјРµРЅРё СЃРЅРёРјРєР°</button>
                </div>
              </div>
              <div className="grid grid-cols-1 sm:grid-cols-2 gap-4">
                {[
                  { label: "РЎРѕР±СЃС‚РІРµРЅРѕ РёРјРµ", val: "РЎС‚РѕСЏРЅ" },
                  { label: "Р¤Р°РјРёР»РёСЏ", val: "РљРѕР»РµРІ" },
                  { label: "РРјРµР№Р»", val: "stoyan@skstroy.bg" },
                  { label: "РўРµР»РµС„РѕРЅ", val: "+359 87 888 9900" },
                ].map(f => (
                  <div key={f.label}>
                    <label className="text-xs text-gray-500 mb-1 block">{f.label}</label>
                    <input
                      defaultValue={f.val}
                      className="w-full px-3 py-2 rounded-xl border border-gray-200 text-sm text-gray-800 focus:outline-none focus:ring-2 focus:ring-blue-500/20 focus:border-blue-400 transition-all"
                    />
                  </div>
                ))}
              </div>
            </>
          )}

          {tab === "notif" && (
            <>
              <p className="text-sm text-gray-800 border-b border-gray-50 pb-3">РќР°СЃС‚СЂРѕР№РєРё Р·Р° РёР·РІРµСЃС‚РёСЏ</p>
              <div className="space-y-4">
                {[
                  { label: "РќРѕРІ РїСЂРѕРµРєС‚ РґРѕР±Р°РІРµРЅ", sub: "РџСЂРё РґРѕР±Р°РІСЏРЅРµ РЅР° РїСЂРѕРµРєС‚ РѕС‚ РµРєРёРїР°" },
                  { label: "Р”РѕРіРѕРІРѕСЂ РїРѕРґРїРёСЃР°РЅ", sub: "РљРѕРіР°С‚Рѕ РєР»РёРµРЅС‚ РїРѕС‚РІСЉСЂРґРё РґРѕРіРѕРІРѕСЂ" },
                  { label: "РљРЎРЎ РіРѕС‚РѕРІР°", sub: "AI РіРµРЅРµСЂРёСЂР°Р» РЅРѕРІР° СЃРјРµС‚РєР°" },
                  { label: "Telegram РёР·РІРµСЃС‚РёСЏ", sub: "РР·РїСЂР°С‚Рё РЅР° С‚РµР»РµС„РѕРЅР° РјРё" },
                  { label: "РРјРµР№Р» РґР°Р№РґР¶РµСЃС‚", sub: "РЎРµРґРјРёС‡РµРЅ РѕР±РѕР±С‰РµРЅ РѕС‚С‡РµС‚" },
                ].map((n, i) => (
                  <label key={n.label} className="flex items-center justify-between cursor-pointer">
                    <div>
                      <p className="text-sm text-gray-700">{n.label}</p>
                      <p className="text-xs text-gray-400">{n.sub}</p>
                    </div>
                    <div className={`relative w-10 h-5.5 rounded-full transition-colors ${i < 3 ? "bg-blue-600" : "bg-gray-200"}`}>
                      <div className={`absolute top-0.5 size-4.5 rounded-full bg-white shadow transition-transform ${i < 3 ? "translate-x-5" : "translate-x-0.5"}`} />
                    </div>
                  </label>
                ))}
              </div>
            </>
          )}

          {tab === "security" && (
            <>
              <p className="text-sm text-gray-800 border-b border-gray-50 pb-3">РЎРёРіСѓСЂРЅРѕСЃС‚</p>
              <div className="space-y-4">
                <div>
                  <label className="text-xs text-gray-500 mb-1 block">РўРµРєСѓС‰Р° РїР°СЂРѕР»Р°</label>
                  <input type="password" defaultValue="вЂўвЂўвЂўвЂўвЂўвЂўвЂўвЂў" className="w-full px-3 py-2 rounded-xl border border-gray-200 text-sm focus:outline-none focus:ring-2 focus:ring-blue-500/20 focus:border-blue-400 transition-all" />
                </div>
                <div>
                  <label className="text-xs text-gray-500 mb-1 block">РќРѕРІР° РїР°СЂРѕР»Р°</label>
                  <input type="password" placeholder="РњРёРЅРёРјСѓРј 8 СЃРёРјРІРѕР»Р°" className="w-full px-3 py-2 rounded-xl border border-gray-200 text-sm placeholder-gray-300 focus:outline-none focus:ring-2 focus:ring-blue-500/20 focus:border-blue-400 transition-all" />
                </div>
                <div className="p-4 rounded-xl bg-emerald-50 border border-emerald-100 flex items-start gap-3">
                  <Shield className="size-4 text-emerald-600 mt-0.5 flex-shrink-0" />
                  <div>
                    <p className="text-sm text-emerald-700">SSL РєСЂРёРїС‚РёСЂР°РЅРµ Р°РєС‚РёРІРЅРѕ</p>
                    <p className="text-xs text-emerald-600 mt-0.5">TLS 1.3 В· Р”Р°РЅРЅРёС‚Рµ СЃР° РЅР°РїСЉР»РЅРѕ Р·Р°С‰РёС‚РµРЅРё</p>
                  </div>
                </div>
              </div>
            </>
          )}

          {tab === "billing" && (
            <>
              <p className="text-sm text-gray-800 border-b border-gray-50 pb-3">РђР±РѕРЅР°РјРµРЅС‚</p>
              <div className="p-4 rounded-2xl bg-gradient-to-r from-amber-50 to-orange-50 border border-amber-200 flex items-start gap-3 mb-4">
                <Crown className="size-5 text-amber-500 flex-shrink-0" />
                <div>
                  <p className="text-sm text-amber-800">РџСЂРµРјРёСѓРј AI РїР»Р°РЅ</p>
                  <p className="text-xs text-amber-600 mt-0.5">449в‚¬/РјРµСЃРµС† В· РЎР»РµРґРІР°С‰Рѕ РїР»Р°С‰Р°РЅРµ: 1 РјР°Р№ 2026</p>
                </div>
              </div>
              <div className="space-y-2">
                {[
                  "в€ћ РїРѕС‚СЂРµР±РёС‚РµР»СЏ",
                  "в€ћ РїСЂРѕРµРєС‚Р° Рё РљРЎРЎ",
                  "AI РјРµРЅРёРґР¶СЉСЂ + РіР»Р°СЃРѕРІРё РєРѕРјР°РЅРґРё",
                  "Telegram РќР•Р—РђР‘РђР’РќРћ",
                  "SLA РїРѕРґРґСЂСЉР¶РєР°",
                  "Р‘СЏР»Р° РµС‚РёРєРµС‚Р°",
                ].map(f => (
                  <div key={f} className="flex items-center gap-2 text-sm text-gray-700">
                    <Check className="size-4 text-teal-500 flex-shrink-0" />
                    {f}
                  </div>
                ))}
              </div>
            </>
          )}

          <div className="pt-3 border-t border-gray-50 flex justify-end">
            <button
              onClick={handleSave}
              className={`flex items-center gap-2 px-5 py-2.5 rounded-xl text-sm transition-all active:scale-95 ${
                saved
                  ? "bg-emerald-600 text-white"
                  : "bg-gradient-to-r from-blue-600 to-teal-600 text-white shadow-md shadow-blue-200 hover:from-blue-700 hover:to-teal-700"
              }`}
            >
              {saved ? <Check className="size-4" /> : <Save className="size-4" />}
              {saved ? "Р—Р°РїР°Р·РµРЅРѕ!" : "Р—Р°РїР°Р·Рё РїСЂРѕРјРµРЅРёС‚Рµ"}
            </button>
          </div>
        </div>
      </div>
    </div>
  );
}



// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ
// FILE: src/app/pages/pro/tools/ProAIOverviewPage.tsx
// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ

import { useState } from "react";
import {
  Sparkles, TrendingUp, TrendingDown, AlertTriangle,
  CheckCircle2, Clock, Zap, RefreshCw, ChevronRight,
} from "lucide-react";

const INSIGHTS = [
  {
    type: "opportunity",
    icon: TrendingUp,
    color: "text-emerald-600",
    bg: "bg-emerald-50",
    border: "border-emerald-100",
    title: "РџСЂРѕРµРєС‚ Р“РµСЂРјР°РЅ РёР·РїСЂРµРІР°СЂРІР° РіСЂР°С„РёРєР° СЃ 8%",
    detail: "РџР»Р°РјРµРЅ РўРѕРґРѕСЂРѕРІ Рё РµРєРёРїСЉС‚ РјСѓ СЂР°Р±РѕС‚СЏС‚ СЃ 15% РїРѕ-РІРёСЃРѕРєР° РµС„РµРєС‚РёРІРЅРѕСЃС‚ РѕС‚ РЅРѕСЂРјР°С‚Р°. РњРѕР¶Рµ РґР° РїСЂРёРєР»СЋС‡Р°С‚ 3 РґРЅРё РїРѕ-СЂР°РЅРѕ.",
    action: "РџСЂРµРіР»РµРґР°Р№ РіСЂР°С„РёРєР°",
  },
  {
    type: "risk",
    icon: AlertTriangle,
    color: "text-amber-600",
    bg: "bg-amber-50",
    border: "border-amber-100",
    title: "РџСЂРѕСЃСЂРѕС‡РµРЅР° С„Р°РєС‚СѓСЂР° Р¤Рљ-2026-025 РѕС‚ Tech Soft OOD",
    detail: "Р¤Р°РєС‚СѓСЂР°С‚Р° Рµ РїСЂРѕСЃСЂРѕС‡РµРЅР° СЃ 5 РґРЅРё. РџСЂРµРїРѕСЂСЉС‡РІР°Рј Р°РІС‚РѕРјР°С‚РёС‡РЅРѕ РЅР°РїРѕРјРЅСЏРЅРµ Рё 2% Р»РёС…РІР° РїСЂРё Р·Р°Р±Р°РІСЏРЅРµ.",
    action: "РР·РїСЂР°С‚Рё РЅР°РїРѕРјРЅСЏРЅРµ",
  },
  {
    type: "insight",
    icon: Zap,
    color: "text-blue-600",
    bg: "bg-blue-50",
    border: "border-blue-100",
    title: "РњР°С‚РµСЂРёР°Р»РёС‚Рµ Р·Р° Р’РёС‚РѕС€Р° 24 СЃРµ РёР·С‡РµСЂРїРІР°С‚",
    detail: "РџСЂРё С‚РµРєСѓС‰РѕС‚Рѕ С‚РµРјРїРѕ, С†РёРјРµРЅС‚Р° С‰Рµ СЃРІСЉСЂС€Рё СЃР»РµРґ 4 РґРЅРё. РџРѕСЂСЉС‡Р°Р№ РјРёРЅРёРјСѓРј 40 С‡СѓРІР°Р»Р° РґРѕ РїРµС‚СЉРє.",
    action: "РќР°РїСЂР°РІРё РїРѕСЂСЉС‡РєР°",
  },
  {
    type: "good",
    icon: CheckCircle2,
    color: "text-teal-600",
    bg: "bg-teal-50",
    border: "border-teal-100",
    title: "6 РѕС‚ 7 СЂР°Р±РѕС‚РЅРёРєР° РёРјР°С‚ РѕС†РµРЅРєР° РЅР°Рґ 4.5 в…",
    detail: "Р•РєРёРїСЉС‚ РїРѕРєР°Р·РІР° РѕС‚Р»РёС‡РЅРѕ РїСЂРµРґСЃС‚Р°РІСЏРЅРµ. РџСЂРµРїРѕСЂСЉС‡РІР°Рј РґР° РЅР°РіСЂР°РґРёС‚Рµ РњРёСЂРѕСЃР»Р°РІ РљРёСЂС‡РµРІ (5.0 в…) СЃ Р±РѕРЅСѓСЃ.",
    action: "Р’РёР¶ РґРµС‚Р°Р№Р»Рё",
  },
  {
    type: "risk",
    icon: TrendingDown,
    color: "text-red-600",
    bg: "bg-red-50",
    border: "border-red-100",
    title: "РџСЂРёС…РѕРґРёС‚Рµ Р·Р° РјР°СЂС‚ СЃР° СЃ 12% РїРѕРґ С‚Р°СЂРіРµС‚Р°",
    detail: "Р Р°Р·Р»РёРєР°С‚Р° Рµ 8 400 Р»РІ. Р“Р»Р°РІРЅР°С‚Р° РїСЂРёС‡РёРЅР° вЂ” Р·Р°Р±Р°РІСЏРЅРµС‚Рѕ РЅР° РїР»Р°С‰Р°РЅРµ РѕС‚ РџРµС‚СЂРѕРІ & РЎРёРЅРѕРІРµ (30 000 Р»РІ).",
    action: "РђРЅР°Р»РёР·РёСЂР°Р№",
  },
];

const STATS = [
  { label:"Р—Р°РІСЉСЂС€РµРЅРё РїСЂРѕРµРєС‚Рё (Q1)",  value:"4",     sub:"в†‘ 1 СЃРїСЂСЏРјРѕ Q4 2025" },
  { label:"РЎСЂРµРґРЅР° РѕС†РµРЅРєР° РєР»РёРµРЅС‚Рё",   value:"4.8 в…", sub:"93% РїСЂРµРїРѕСЂСЉС‡РІР°С‚" },
  { label:"AI РїСЂРµРґР»РѕР¶РµРЅРёСЏ РёР·РїСЉР»РЅРµРЅРё",value:"78%",   sub:"14 РѕС‚ 18 С‚Р°Р·Рё СЃРµРґРјРёС†Р°" },
  { label:"РРєРѕРЅРѕРјРёРё РѕС‚ AI",          value:"3 200 Р»РІ",sub:"РѕС‚ РѕРїС‚РёРјРёР·Р°С†РёРё" },
];

export function ProAIOverviewPage() {
  const [refreshing, setRefreshing] = useState(false);
  const [dismissed, setDismissed] = useState<Set<number>>(new Set());

  const refresh = () => {
    setRefreshing(true);
    setDismissed(new Set());
    setTimeout(() => setRefreshing(false), 1500);
  };

  const visible = INSIGHTS.filter((_, i) => !dismissed.has(i));

  return (
    <div className="p-5 lg:p-7 space-y-6">
      {/* Header */}
      <div className="flex items-center justify-between">
        <div className="flex items-center gap-3">
          <div className="size-10 rounded-2xl bg-gradient-to-br from-blue-600 to-teal-500 flex items-center justify-center shadow-md shadow-blue-200">
            <Sparkles className="size-5 text-white" />
          </div>
          <div>
            <h1 className="text-xl text-gray-800">AI РћРіР»РµРґ</h1>
            <p className="text-sm text-gray-500">РђРІС‚РѕРјР°С‚РёС‡РµРЅ Р°РЅР°Р»РёР· РЅР° Р±РёР·РЅРµСЃР° РІРё РѕС‚ ZENITH AI</p>
          </div>
        </div>
        <button onClick={refresh} className={`flex items-center gap-2 px-3 py-2 rounded-xl border border-gray-200 text-sm text-gray-600 bg-white hover:bg-gray-50 transition-all ${refreshing ? "pointer-events-none" : ""}`}>
          <RefreshCw className={`size-4 ${refreshing ? "animate-spin text-blue-600" : ""}`} />
          {refreshing ? "РђРЅР°Р»РёР·РёСЂР°..." : "РћР±РЅРѕРІРё"}
        </button>
      </div>

      {/* Quick stats */}
      <div className="grid grid-cols-2 lg:grid-cols-4 gap-4">
        {STATS.map(s => (
          <div key={s.label} className="bg-white rounded-2xl border border-gray-100 p-4">
            <p className="text-xl text-gray-800">{s.value}</p>
            <p className="text-xs text-gray-500 mt-0.5">{s.label}</p>
            <p className="text-[10px] text-emerald-600 mt-1">{s.sub}</p>
          </div>
        ))}
      </div>

      {/* AI Insights */}
      <div>
        <div className="flex items-center gap-2 mb-3">
          <Sparkles className="size-4 text-blue-600" />
          <p className="text-sm text-gray-700">AI РџСЂРµРїРѕСЂСЉРєРё Рё РїСЂРµРґСѓРїСЂРµР¶РґРµРЅРёСЏ</p>
          <span className="ml-1 px-2 py-0.5 rounded-full bg-blue-50 text-blue-600 text-xs">{visible.length}</span>
        </div>
        <div className="space-y-3">
          {visible.map((ins, idx) => {
            const Icon = ins.icon;
            const origIdx = INSIGHTS.indexOf(ins);
            return (
              <div key={origIdx} className={`bg-white rounded-2xl border ${ins.border} p-4 hover:shadow-sm transition-all`}>
                <div className="flex items-start gap-3">
                  <div className={`size-9 rounded-xl ${ins.bg} flex items-center justify-center flex-shrink-0 mt-0.5`}>
                    <Icon className={`size-4 ${ins.color}`} />
                  </div>
                  <div className="flex-1 min-w-0">
                    <p className="text-sm text-gray-800">{ins.title}</p>
                    <p className="text-xs text-gray-500 mt-1 leading-relaxed">{ins.detail}</p>
                  </div>
                </div>
                <div className="flex items-center gap-2 mt-3">
                  <button className={`flex items-center gap-1.5 px-3 py-1.5 rounded-xl text-xs transition-all ${ins.bg} ${ins.color} hover:opacity-80`}>
                    {ins.action} <ChevronRight className="size-3" />
                  </button>
                  <button onClick={() => setDismissed(prev => new Set([...prev, origIdx]))} className="px-3 py-1.5 rounded-xl text-xs text-gray-400 hover:bg-gray-100 transition-all">
                    РћС‚С…РІСЉСЂР»Рё
                  </button>
                </div>
              </div>
            );
          })}
          {visible.length === 0 && (
            <div className="text-center py-8 text-sm text-gray-400">
              Р’СЃРёС‡РєРё РїСЂРµРїРѕСЂСЉРєРё СЃР° СЂР°Р·РіР»РµРґР°РЅРё. РќР°С‚РёСЃРЅРё "РћР±РЅРѕРІРё" Р·Р° РЅРѕРІ Р°РЅР°Р»РёР·.
            </div>
          )}
        </div>
      </div>

      {/* Weekly summary */}
      <div className="bg-gradient-to-br from-blue-50 to-teal-50 rounded-2xl border border-blue-100 p-5">
        <div className="flex items-center gap-2 mb-3">
          <Clock className="size-4 text-blue-600" />
          <p className="text-sm text-gray-700">РЎРµРґРјРёС‡РЅРѕ РѕР±РѕР±С‰РµРЅРёРµ вЂ” 31 РјР°СЂС‚вЂ“4 Р°РїСЂ 2026</p>
        </div>
        <p className="text-sm text-gray-600 leading-relaxed">
          РўР°Р·Рё СЃРµРґРјРёС†Р° Р±СЏС…Р° РѕР±СЂР°Р±РѕС‚РµРЅРё <span className="text-blue-700">3 РЅРѕРІРё Р·Р°РїРёС‚РІР°РЅРёСЏ</span>, РёР·РґР°РґРµРЅРё <span className="text-blue-700">2 С„Р°РєС‚СѓСЂРё</span> РЅР° СЃС‚РѕР№РЅРѕСЃС‚ 43 200 Р»РІ Рё Р·Р°РІСЉСЂС€РµРЅР° <span className="text-blue-700">1 РљРЎРЎ</span>. Р•РєРёРїСЉС‚ РїРѕРєР°Р·РІР° СЃС‚Р°Р±РёР»РЅРѕСЃС‚. РћСЃРЅРѕРІРЅРѕС‚Рѕ РІРЅРёРјР°РЅРёРµ С‚СЂСЏР±РІР° РґР° Р±СЉРґРµ РЅР°СЃРѕС‡РµРЅРѕ РєСЉРј СЃСЉР±РёСЂР°РЅРµС‚Рѕ РЅР° РїСЂРѕСЃСЂРѕС‡РµРЅРё РїР»Р°С‰Р°РЅРёСЏ.
        </p>
      </div>
    </div>
  );
}



// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ
// FILE: src/app/pages/pro/tools/Pro3DVisualizerPage.tsx
// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ

import { useState } from "react";
import {
  Box, RotateCcw, ZoomIn, ZoomOut, Layers,
  Sun, Eye, Download, Share2, Maximize2, Play,
  Move3D, Palette,
} from "lucide-react";

const PROJECTS_3D = [
  { id:"1", name:"Р’РёР»Р° СЃ. Р“РµСЂРјР°РЅ вЂ” С„Р°СЃР°РґР°", type:"Р–РёР»РёС‰РЅР°", stage:"РћСЃРЅРѕРІРё + Р“СЂСѓР± СЃС‚СЂРѕРµР¶", thumb:"рџЏЎ", color:"from-teal-400 to-emerald-500" },
  { id:"2", name:"Р’РёС‚РѕС€Р° 24 вЂ” Р°РїР°СЂС‚Р°РјРµРЅС‚",  type:"Р–РёР»РёС‰РЅР°", stage:"Р’СЉС‚СЂРµС€РµРЅ СЂРµРјРѕРЅС‚",       thumb:"рџЏ ", color:"from-blue-400 to-violet-500" },
  { id:"3", name:"РћС„РёСЃ РҐСЂ. Р‘РѕС‚РµРІ 12",       type:"РўСЉСЂРіРѕРІСЃРєР°",stage:"РћР±Р·Р°РІРµР¶РґР°РЅРµ",           thumb:"рџЏў", color:"from-amber-400 to-orange-500" },
];

const MATERIALS = [
  { name:"РљР»РёРЅРєРµСЂ С‚СѓС…Р»Рё",  color:"#C4A882", selected:true  },
  { name:"Р‘СЏР»Р° РјР°Р·РёР»РєР°",   color:"#F5F0E8", selected:false },
  { name:"РўСЉРјРµРЅ Р±РµС‚РѕРЅ",    color:"#6B6B6B", selected:false },
  { name:"Р”СЉСЂРІРµРЅР° Р»Р°РјРїРµСЂРёСЏ",color:"#8B6914",selected:false },
  { name:"РЎС‚СЉРєР»Рѕ / Р°Р»СѓРјРёРЅРёР№",color:"#9FC5E8",selected:false },
];

const VIEWS = ["Р¤СЂРѕРЅС‚","РЎС‚СЂР°РЅР°","Р—Р°РґРЅР°","Р“РѕСЂРµ","РџРµСЂСЃРїРµРєС‚РёРІР°","РРЅС‚РµСЂРёРѕСЂ"];

export function Pro3DVisualizerPage() {
  const [selectedProject, setSelectedProject] = useState(PROJECTS_3D[0]);
  const [activeView, setActiveView] = useState("РџРµСЂСЃРїРµРєС‚РёРІР°");
  const [materials, setMaterials] = useState(MATERIALS);
  const [lightMode, setLightMode] = useState<"day"|"sunset"|"night">("day");
  const [showLayers, setShowLayers] = useState(false);
  const [zoom, setZoom] = useState(100);

  const toggleMaterial = (name: string) =>
    setMaterials(prev => prev.map(m => ({ ...m, selected: m.name === name })));

  return (
    <div className="p-5 lg:p-7 space-y-5">
      {/* Header */}
      <div className="flex items-center justify-between">
        <div>
          <h1 className="text-xl text-gray-800">3D Р’РёР·СѓР°Р»РёР·Р°С‚РѕСЂ</h1>
          <p className="text-sm text-gray-500 mt-0.5">РџСЂРµРіР»РµРґР°Р№ РїСЂРѕРµРєС‚Р° РІ 3D РїСЂРµРґРё РёР·РіСЂР°Р¶РґР°РЅРµ</p>
        </div>
        <div className="flex items-center gap-2">
          <button className="flex items-center gap-2 px-3 py-2 rounded-xl border border-gray-200 text-sm text-gray-600 bg-white hover:bg-gray-50 transition-all">
            <Share2 className="size-4" />
            РЎРїРѕРґРµР»Рё
          </button>
          <button className="flex items-center gap-2 px-3 py-2 rounded-xl bg-gradient-to-r from-blue-600 to-teal-600 text-white text-sm hover:from-blue-700 hover:to-teal-700 shadow-md shadow-blue-200 transition-all active:scale-95">
            <Download className="size-4" />
            РР·С‚РµРіР»Рё
          </button>
        </div>
      </div>

      {/* Project selector */}
      <div className="flex gap-3 overflow-x-auto pb-1">
        {PROJECTS_3D.map(p => (
          <button key={p.id} onClick={() => setSelectedProject(p)}
            className={`flex-shrink-0 flex items-center gap-3 px-4 py-3 rounded-2xl border transition-all ${selectedProject.id===p.id ? "border-blue-300 bg-blue-50" : "border-gray-100 bg-white hover:bg-gray-50"}`}>
            <div className={`size-10 rounded-xl bg-gradient-to-br ${p.color} flex items-center justify-center text-xl`}>
              {p.thumb}
            </div>
            <div className="text-left">
              <p className={`text-sm ${selectedProject.id===p.id ? "text-blue-700" : "text-gray-700"}`}>{p.name}</p>
              <p className="text-xs text-gray-400">{p.stage}</p>
            </div>
          </button>
        ))}
      </div>

      <div className="grid grid-cols-1 lg:grid-cols-4 gap-5">
        {/* 3D Canvas area */}
        <div className="lg:col-span-3">
          <div className="bg-gradient-to-br from-gray-100 to-gray-200 rounded-2xl border border-gray-200 overflow-hidden" style={{ minHeight: 420 }}>
            {/* Toolbar */}
            <div className="flex items-center gap-1 px-4 py-2.5 bg-white/80 backdrop-blur-sm border-b border-gray-200">
              {VIEWS.map(v => (
                <button key={v} onClick={() => setActiveView(v)}
                  className={`px-2.5 py-1 rounded-lg text-xs transition-all ${activeView===v ? "bg-blue-600 text-white" : "text-gray-600 hover:bg-gray-100"}`}>
                  {v}
                </button>
              ))}
              <div className="flex-1" />
              <button onClick={() => setZoom(z => Math.min(z+20,200))} className="size-7 flex items-center justify-center rounded-lg text-gray-500 hover:bg-gray-100 transition-colors"><ZoomIn className="size-4" /></button>
              <span className="text-xs text-gray-500 w-10 text-center">{zoom}%</span>
              <button onClick={() => setZoom(z => Math.max(z-20,40))} className="size-7 flex items-center justify-center rounded-lg text-gray-500 hover:bg-gray-100 transition-colors"><ZoomOut className="size-4" /></button>
              <button onClick={() => setZoom(100)} className="size-7 flex items-center justify-center rounded-lg text-gray-500 hover:bg-gray-100 transition-colors"><RotateCcw className="size-4" /></button>
              <button className="size-7 flex items-center justify-center rounded-lg text-gray-500 hover:bg-gray-100 transition-colors"><Maximize2 className="size-4" /></button>
            </div>

            {/* Viewport */}
            <div className="relative flex items-center justify-center" style={{ height: 360 }}>
              {/* Simulated 3D building */}
              <div className="relative" style={{ transform: `scale(${zoom/100})`, transition:"transform 0.3s" }}>
                {/* Base */}
                <div className="relative mx-auto" style={{ width: 280, height: 200 }}>
                  {/* Shadow */}
                  <div className="absolute bottom-0 left-4 right-4 h-8 rounded-full bg-black/10 blur-md" />
                  {/* Building body */}
                  <div className="absolute bottom-10 left-10 right-10 rounded-t-3xl overflow-hidden" style={{
                    height: 170,
                    background: materials.find(m=>m.selected)?.color ?? "#C4A882",
                    boxShadow: "inset -4px 0 20px rgba(0,0,0,0.15), 4px 8px 24px rgba(0,0,0,0.2)",
                  }}>
                    {/* Windows */}
                    <div className="grid grid-cols-3 gap-3 p-4 pt-6">
                      {[...Array(9)].map((_,i) => (
                        <div key={i} className="rounded-md aspect-square" style={{
                          background: lightMode==="night" ? "rgba(255,220,100,0.8)" : "rgba(255,255,255,0.7)",
                          boxShadow: "inset 0 1px 3px rgba(0,0,0,0.1)",
                        }} />
                      ))}
                    </div>
                    {/* Door */}
                    <div className="mx-auto mt-2 rounded-t-xl" style={{ width:36, height:48, background:"rgba(60,40,20,0.6)" }} />
                  </div>
                  {/* Roof */}
                  <div className="absolute" style={{
                    bottom: 180, left: 4, right: 4, height: 40,
                    background: lightMode==="night" ? "#1a1a2e" : "#8B4513",
                    clipPath:"polygon(0 100%,50% 0,100% 100%)",
                  }} />
                  {/* Ground */}
                  <div className="absolute bottom-0 left-0 right-0 h-10 rounded-b-xl" style={{ background: lightMode==="sunset" ? "#6B4226" : "#4a7c59" }} />
                </div>

                {/* Light indicator */}
                {lightMode === "day" && (
                  <div className="absolute -top-8 right-0">
                    <Sun className="size-8 text-amber-400 animate-pulse" />
                  </div>
                )}
              </div>

              {/* Controls overlay */}
              <div className="absolute bottom-3 right-3 flex gap-1.5">
                {(["day","sunset","night"] as const).map(mode => (
                  <button key={mode} onClick={() => setLightMode(mode)}
                    className={`px-2.5 py-1 rounded-full text-xs transition-all ${lightMode===mode ? "bg-white/90 text-gray-800 shadow-sm" : "bg-black/20 text-white hover:bg-black/30"}`}>
                    {{ day:"вЂпёЏ Р”РµРЅ", sunset:"рџЊ… Р—Р°Р»РµР·", night:"рџЊ™ РќРѕС‰" }[mode]}
                  </button>
                ))}
              </div>

              <div className="absolute top-3 left-3 flex gap-1.5">
                <div className="bg-white/80 backdrop-blur-sm rounded-xl px-3 py-1.5">
                  <p className="text-xs text-gray-700">{selectedProject.name}</p>
                  <p className="text-[10px] text-gray-400">{activeView} В· {zoom}%</p>
                </div>
              </div>
            </div>
          </div>

          {/* Drag hint */}
          <div className="flex items-center justify-center gap-2 mt-2">
            <Move3D className="size-3.5 text-gray-400" />
            <p className="text-xs text-gray-400">Р—Р°РІСЉСЂС‚Рё СЃ РјРёС€РєР°С‚Р° В· РЎРєСЂРѕР»РёСЂР°Р№ Р·Р° Р·СѓРј</p>
          </div>
        </div>

        {/* Right panel */}
        <div className="space-y-4">
          {/* Material picker */}
          <div className="bg-white rounded-2xl border border-gray-100 p-4">
            <div className="flex items-center gap-2 mb-3">
              <Palette className="size-4 text-blue-600" />
              <p className="text-sm text-gray-700">РњР°С‚РµСЂРёР°Р»Рё</p>
            </div>
            <div className="space-y-2">
              {materials.map(m => (
                <button key={m.name} onClick={() => toggleMaterial(m.name)}
                  className={`w-full flex items-center gap-3 px-3 py-2 rounded-xl transition-all ${m.selected ? "bg-blue-50 border border-blue-200" : "hover:bg-gray-50 border border-transparent"}`}>
                  <div className="size-5 rounded-full border border-gray-200 flex-shrink-0" style={{ background: m.color }} />
                  <span className="text-xs text-gray-700">{m.name}</span>
                  {m.selected && <span className="ml-auto text-blue-600 text-xs">вњ“</span>}
                </button>
              ))}
            </div>
          </div>

          {/* Layers */}
          <div className="bg-white rounded-2xl border border-gray-100 p-4">
            <button onClick={() => setShowLayers(s=>!s)} className="w-full flex items-center gap-2 mb-2">
              <Layers className="size-4 text-teal-600" />
              <p className="text-sm text-gray-700">РЎР»РѕРµРІРµ</p>
              <span className={`ml-auto size-5 flex items-center justify-center rounded-full bg-gray-100 text-gray-500 text-xs transition-transform ${showLayers?"rotate-90":""}`}>вЂє</span>
            </button>
            {showLayers && (
              <div className="space-y-1">
                {["РљРѕРЅСЃС‚СЂСѓРєС†РёСЏ","Р¤Р°СЃР°РґР°","РџСЂРѕР·РѕСЂС†Рё","РџРѕРєСЂРёРІ","Р›Р°РЅРґС€Р°С„С‚"].map(l => (
                  <label key={l} className="flex items-center gap-2 px-2 py-1.5 rounded-lg hover:bg-gray-50 cursor-pointer">
                    <input type="checkbox" defaultChecked className="rounded" />
                    <span className="text-xs text-gray-600">{l}</span>
                  </label>
                ))}
              </div>
            )}
          </div>

          {/* Generate button */}
          <button className="w-full flex items-center justify-center gap-2 py-3 rounded-2xl bg-gradient-to-r from-blue-600 to-teal-600 text-white text-sm hover:from-blue-700 hover:to-teal-700 shadow-md shadow-blue-200 transition-all active:scale-95">
            <Play className="size-4" />
            AI Р“РµРЅРµСЂРёСЂР°Р№ 3D
          </button>
        </div>
      </div>
    </div>
  );
}



// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ
// FILE: src/app/pages/pro/tools/ProSketchPage.tsx
// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ

import { useState, useRef, useEffect } from "react";
import {
  Pencil, Square, Circle, Minus, Eraser, Download,
  RotateCcw, ZoomIn, ZoomOut, Layers, Sparkles,
  MousePointer, Trash2, Type,
} from "lucide-react";

type Tool = "select"|"pen"|"rect"|"circle"|"line"|"eraser"|"text";

interface DrawItem {
  id: string;
  tool: Tool;
  color: string;
  size: number;
  points?: number[];
  x?: number; y?: number; w?: number; h?: number;
  text?: string;
}

const COLORS = ["#1e293b","#2563EB","#0D9488","#f59e0b","#ef4444","#8b5cf6","#ffffff"];
const SIZES  = [1, 2, 4, 6, 10];

const AI_SUGGESTIONS = [
  "Р”РѕР±Р°РІРё СЂР°Р·РјРµСЂРё Рё Р»РµРіРµРЅРґР°",
  "РџСЂРѕРІРµСЂРё РїСЂРѕРїРѕСЂС†РёРёС‚Рµ РЅР° СЃС‚Р°РёС‚Рµ",
  "РџСЂРµРґР»РѕР¶Рё РїРѕСЃС‚Р°РІСЏРЅРµ РЅР° РјРѕРєСЂРё РїРѕРјРµС‰РµРЅРёСЏ",
  "Р“РµРЅРµСЂРёСЂР°Р№ РљРЎРЎ РѕС‚ СЃРєРёС†Р°С‚Р°",
];

export function ProSketchPage() {
  const canvasRef = useRef<HTMLCanvasElement>(null);
  const [activeTool, setActiveTool] = useState<Tool>("pen");
  const [color, setColor] = useState("#1e293b");
  const [size, setSize] = useState(2);
  const [drawing, setDrawing] = useState(false);
  const [paths, setPaths] = useState<{ points: [number,number][]; color: string; size: number }[]>([]);
  const [currentPath, setCurrentPath] = useState<[number,number][]>([]);
  const [history, setHistory] = useState<typeof paths>([]);

  const getPos = (e: React.MouseEvent<HTMLCanvasElement> | React.TouchEvent<HTMLCanvasElement>): [number,number] => {
    const canvas = canvasRef.current!;
    const rect = canvas.getBoundingClientRect();
    if ("touches" in e) {
      return [e.touches[0].clientX - rect.left, e.touches[0].clientY - rect.top];
    }
    return [e.clientX - rect.left, e.clientY - rect.top];
  };

  const startDraw = (e: React.MouseEvent<HTMLCanvasElement>) => {
    if (activeTool !== "pen" && activeTool !== "eraser") return;
    setDrawing(true);
    setCurrentPath([getPos(e)]);
  };
  const continueDraw = (e: React.MouseEvent<HTMLCanvasElement>) => {
    if (!drawing) return;
    setCurrentPath(prev => [...prev, getPos(e)]);
  };
  const stopDraw = () => {
    if (!drawing) return;
    setDrawing(false);
    if (currentPath.length > 1) {
      setPaths(prev => [...prev, { points: currentPath, color: activeTool==="eraser"?"#f8fafc":color, size: activeTool==="eraser"?16:size }]);
      setHistory([]);
    }
    setCurrentPath([]);
  };

  useEffect(() => {
    const canvas = canvasRef.current;
    if (!canvas) return;
    const ctx = canvas.getContext("2d")!;
    ctx.clearRect(0, 0, canvas.width, canvas.height);
    // Grid
    ctx.strokeStyle = "#e5e7eb"; ctx.lineWidth = 0.5;
    for (let x=0; x<canvas.width; x+=20) { ctx.beginPath(); ctx.moveTo(x,0); ctx.lineTo(x,canvas.height); ctx.stroke(); }
    for (let y=0; y<canvas.height; y+=20) { ctx.beginPath(); ctx.moveTo(0,y); ctx.lineTo(canvas.width,y); ctx.stroke(); }
    // Paths
    [...paths, ...(currentPath.length>1 ? [{ points:currentPath, color: activeTool==="eraser"?"#f8fafc":color, size: activeTool==="eraser"?16:size }] : [])].forEach(p => {
      if (p.points.length < 2) return;
      ctx.beginPath();
      ctx.strokeStyle = p.color; ctx.lineWidth = p.size;
      ctx.lineCap = "round"; ctx.lineJoin = "round";
      ctx.moveTo(p.points[0][0], p.points[0][1]);
      p.points.slice(1).forEach(([x,y]) => ctx.lineTo(x,y));
      ctx.stroke();
    });
  }, [paths, currentPath, color, size, activeTool]);

  const undo = () => {
    if (paths.length === 0) return;
    setHistory(prev => [paths[paths.length-1], ...prev]);
    setPaths(prev => prev.slice(0,-1));
  };
  const redo = () => {
    if (history.length === 0) return;
    setPaths(prev => [...prev, history[0]]);
    setHistory(prev => prev.slice(1));
  };
  const clear = () => { setPaths([]); setHistory([]); };

  const download = () => {
    const canvas = canvasRef.current;
    if (!canvas) return;
    const link = document.createElement("a");
    link.download = "sketch_temadom.png";
    link.href = canvas.toDataURL();
    link.click();
  };

  const TOOLS: { id: Tool; icon: typeof Pencil; label: string }[] = [
    { id:"select", icon:MousePointer, label:"РР·Р±РѕСЂ" },
    { id:"pen",    icon:Pencil,       label:"РњРѕР»РёРІ" },
    { id:"rect",   icon:Square,       label:"РџСЂР°РІРѕСЉРіСЉР»РЅРёРє" },
    { id:"circle", icon:Circle,       label:"РљСЂСЉРі" },
    { id:"line",   icon:Minus,        label:"Р›РёРЅРёСЏ" },
    { id:"text",   icon:Type,         label:"РўРµРєСЃС‚" },
    { id:"eraser", icon:Eraser,       label:"Р“СѓРјР°" },
  ];

  return (
    <div className="p-5 lg:p-7 space-y-4">
      <div className="flex items-center justify-between">
        <div>
          <h1 className="text-xl text-gray-800">IA Sketch</h1>
          <p className="text-sm text-gray-500 mt-0.5">Р•СЃРєРёР·РёСЂР°Р№ РїР»Р°РЅРѕРІРµ Рё СЃС…РµРјРё СЃ AI РїРѕРјРѕС‰</p>
        </div>
        <div className="flex items-center gap-2">
          <button onClick={undo} className="size-9 flex items-center justify-center rounded-xl border border-gray-200 text-gray-500 hover:bg-gray-50 transition-all"><RotateCcw className="size-4" /></button>
          <button onClick={clear} className="size-9 flex items-center justify-center rounded-xl border border-red-100 text-red-500 hover:bg-red-50 transition-all"><Trash2 className="size-4" /></button>
          <button onClick={download} className="flex items-center gap-2 px-3 py-2 rounded-xl bg-gradient-to-r from-blue-600 to-teal-600 text-white text-sm hover:from-blue-700 hover:to-teal-700 shadow-md shadow-blue-200 transition-all active:scale-95">
            <Download className="size-4" />
            РР·С‚РµРіР»Рё
          </button>
        </div>
      </div>

      <div className="flex flex-col lg:flex-row gap-4">
        {/* Toolbar */}
        <div className="flex lg:flex-col gap-1 bg-white rounded-2xl border border-gray-100 p-2 h-fit">
          {TOOLS.map(t => {
            const Icon = t.icon;
            return (
              <button key={t.id} onClick={() => setActiveTool(t.id)} title={t.label}
                className={`size-9 flex items-center justify-center rounded-xl transition-all ${activeTool===t.id ? "bg-blue-600 text-white shadow-md shadow-blue-200" : "text-gray-500 hover:bg-gray-100"}`}>
                <Icon className="size-4" />
              </button>
            );
          })}
          <div className="w-full h-px bg-gray-100 my-1" />
          {/* Sizes */}
          {SIZES.map(s => (
            <button key={s} onClick={() => setSize(s)} title={`Р Р°Р·РјРµСЂ ${s}`}
              className={`size-9 flex items-center justify-center rounded-xl transition-all ${size===s ? "bg-teal-50 border border-teal-200" : "hover:bg-gray-50"}`}>
              <div className="rounded-full bg-gray-700" style={{ width: s*2+2, height: s*2+2 }} />
            </button>
          ))}
        </div>

        {/* Canvas */}
        <div className="flex-1 space-y-3">
          <div className="bg-white rounded-2xl border border-gray-200 overflow-hidden shadow-sm">
            {/* Color bar */}
            <div className="flex items-center gap-2 px-4 py-2 border-b border-gray-100">
              {COLORS.map(c => (
                <button key={c} onClick={() => setColor(c)}
                  className={`size-6 rounded-full border-2 transition-all hover:scale-110 ${color===c ? "border-blue-500 scale-110" : "border-gray-200"}`}
                  style={{ background: c }}
                />
              ))}
              <div className="flex-1" />
              <span className="text-xs text-gray-400">{paths.length} РѕР±РµРєС‚Рё</span>
            </div>
            <canvas
              ref={canvasRef}
              width={900} height={560}
              onMouseDown={startDraw}
              onMouseMove={continueDraw}
              onMouseUp={stopDraw}
              onMouseLeave={stopDraw}
              style={{ cursor: activeTool==="eraser"?"cell": activeTool==="pen"?"crosshair":"default", width:"100%", height:"auto", maxHeight:480, background:"#f8fafc" }}
              className="block"
            />
          </div>

          {/* AI suggestions */}
          <div className="bg-gradient-to-r from-blue-50 to-teal-50 rounded-2xl border border-blue-100 p-4">
            <div className="flex items-center gap-2 mb-2">
              <Sparkles className="size-4 text-blue-600" />
              <p className="text-sm text-gray-700">AI РїСЂРµРґР»РѕР¶РµРЅРёСЏ</p>
            </div>
            <div className="flex flex-wrap gap-2">
              {AI_SUGGESTIONS.map(s => (
                <button key={s} className="px-3 py-1.5 rounded-xl text-xs bg-white border border-blue-200 text-blue-700 hover:bg-blue-50 hover:border-blue-300 transition-all">
                  {s}
                </button>
              ))}
            </div>
          </div>
        </div>
      </div>
    </div>
  );
}



// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ
// FILE: src/app/pages/pro/tools/ProAIAssistantToolPage.tsx
// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ

import { useState, useRef, useEffect } from "react";
import { Sparkles, Send, Paperclip, Mic, Bot, User, Copy, ThumbsUp, ThumbsDown, Zap } from "lucide-react";

interface Message { id: string; role: "user"|"ai"; text: string; time: string; }

const QUICK_PROMPTS = [
  "РљР°РєСЉРІ Рµ СЃСЂРµРґРЅРёСЏС‚ Р±СЋРґР¶РµС‚ Р·Р° СЂРµРјРѕРЅС‚ РЅР° 80РєРІ. Р°РїР°СЂС‚Р°РјРµРЅС‚?",
  "РќР°РїРёС€Рё РїСЂРёРјРµСЂРµРЅ РґРѕРіРѕРІРѕСЂ Р·Р° СЃС‚СЂРѕРёС‚РµР»СЃС‚РІРѕ",
  "РљР°Рє РґР° РёР·С‡РёСЃР»СЏ С†РµРЅР°С‚Р° РЅР° РјР°С‚РµСЂРёР°Р»РёС‚Рµ Р·Р° РљРЎРЎ?",
  "Р”Р°Р№ РјРё СЃСЉРІРµС‚Рё Р·Р° СѓРїСЂР°РІР»РµРЅРёРµ РЅР° СЂР°Р±РѕС‚РЅРёС†Рё РЅР° РѕР±РµРєС‚",
  "РљР°РєРІРё СЃР° Р·Р°РґСЉР»Р¶РёС‚РµР»РЅРёС‚Рµ РґРѕРєСѓРјРµРЅС‚Рё Р·Р° СЃС‚СЂРѕРёС‚РµР»РµРЅ Р°РєС‚ 15?",
  "РљР°Рє РґР° РїРѕРґРѕР±СЂСЏ cashflow-Р° РЅР° СЃС‚СЂРѕРёС‚РµР»РЅР° С„РёСЂРјР°?",
];

const INITIAL: Message[] = [
  {
    id: "1", role:"ai",
    text:"Р—РґСЂР°РІРµР№! РђР· СЃСЉРј ZENITH AI вЂ” РІР°С€РёСЏС‚ СЃС‚СЂРѕРёС‚РµР»РµРЅ Р±РёР·РЅРµСЃ Р°СЃРёСЃС‚РµРЅС‚. РњРѕРіР° РґР° РІРё РїРѕРјРѕРіРЅР° СЃ:\n\nвЂў **Р”РѕРіРѕРІРѕСЂРё Рё РґРѕРєСѓРјРµРЅС‚Рё** вЂ” РіРµРЅРµСЂРёСЂР°Рј, СЂРµРґР°РєС‚РёСЂР°Рј, РѕР±СЏСЃРЅСЏРІР°Рј\nвЂў **РљРЎРЎ Рё РѕС†РµРЅРєРё** вЂ” РёР·С‡РёСЃР»РµРЅРёСЏ, РїСЂРѕРІРµСЂРєРё, РѕРїС‚РёРјРёР·Р°С†РёРё\nвЂў **Р‘РёР·РЅРµСЃ СЃСЉРІРµС‚Рё** вЂ” С†РµРЅРѕРѕР±СЂР°Р·СѓРІР°РЅРµ, СѓРїСЂР°РІР»РµРЅРёРµ, СЂР°СЃС‚РµР¶\nвЂў **РџСЂР°РІРЅРё РІСЉРїСЂРѕСЃРё** вЂ” РЅР°СЂРµРґР±Рё, СЂР°Р·СЂРµС€РёС‚РµР»РЅРё, Р°РєС‚РѕРІРµ\nвЂў **РўРµС…РЅРёС‡РµСЃРєРё РІСЉРїСЂРѕСЃРё** вЂ” РјР°С‚РµСЂРёР°Р»Рё, С‚РµС…РЅРѕР»РѕРіРёРё, СЃС‚Р°РЅРґР°СЂС‚Рё\n\nРЎ РєР°РєРІРѕ РјРѕРіР° РґР° РІРё РїРѕРјРѕРіРЅР° РґРЅРµСЃ?",
    time:"СЃРµРіР°",
  },
];

const AI_RESPONSES: Record<string, string> = {
  "default": "Р Р°Р·Р±РёСЂР°Рј РІСЉРїСЂРѕСЃР° РІРё. Р‘Р°Р·РёСЂР°Р№РєРё СЃРµ РЅР° РґР°РЅРЅРёС‚Рµ РѕС‚ РІР°С€Р°С‚Р° С„РёСЂРјР° РЎРљ РЎС‚СЂРѕР№ Р•РћРћР” Рё РЅР°СЃС‚РѕСЏС‰РёСЏ РїР°Р·Р°СЂ РІ Р‘СЉР»РіР°СЂРёСЏ, РµС‚Рѕ РјРѕСЏС‚ Р°РЅР°Р»РёР·:\n\nР—Р° СЃС‚СЂРѕРёС‚РµР»РµРЅ Р±РёР·РЅРµСЃ СЃ РІР°С€РёСЏ РїСЂРѕС„РёР» (3 Р°РєС‚РёРІРЅРё РїСЂРѕРµРєС‚Р°, 8 СЂР°Р±РѕС‚РЅРёРєР°, РіРѕРґРёС€РµРЅ РѕР±РѕСЂРѕС‚ ~150-200Рє Р»РІ), РїСЂРµРїРѕСЂСЉС‡РІР°Рј:\n\n1. **РџСЂРёРѕСЂРёС‚РµС‚ 1** вЂ” РЎСЉР±РёСЂР°РЅРµ РЅР° РїСЂРѕСЃСЂРѕС‡РµРЅРё РІР·РµРјР°РЅРёСЏ (36 900 Р»РІ)\n2. **РџСЂРёРѕСЂРёС‚РµС‚ 2** вЂ” РћРїС‚РёРјРёР·Р°С†РёСЏ РЅР° РјР°С‚РµСЂРёР°Р»РЅРёС‚Рµ СЂР°Р·С…РѕРґРё (~15% РїРѕС‚РµРЅС†РёР°Р»)\n3. **РџСЂРёРѕСЂРёС‚РµС‚ 3** вЂ” Р”РёРґР¶РёС‚Р°Р»РёР·Р°С†РёСЏ РЅР° РґРѕРєСѓРјРµРЅС‚РѕРѕР±РѕСЂРѕС‚Р°\n\nРСЃРєР°С‚Рµ Р»Рё РґР° СЂР°Р·СЂР°Р±РѕС‚РёРј РїР»Р°РЅ Р·Р° РґРµР№СЃС‚РІРёРµ РїРѕ РЅСЏРєРѕР№ РѕС‚ С‚РµР·Рё С‚РѕС‡РєРё?",
};

export function ProAIAssistantToolPage() {
  const [messages, setMessages] = useState<Message[]>(INITIAL);
  const [input, setInput] = useState("");
  const [loading, setLoading] = useState(false);
  const endRef = useRef<HTMLDivElement>(null);

  useEffect(() => { endRef.current?.scrollIntoView({ behavior:"smooth" }); }, [messages]);

  const send = (text?: string) => {
    const txt = (text ?? input).trim();
    if (!txt || loading) return;
    const userMsg: Message = { id: Date.now().toString(), role:"user", text: txt, time: new Date().toLocaleTimeString("bg-BG",{hour:"2-digit",minute:"2-digit"}) };
    setMessages(prev => [...prev, userMsg]);
    setInput("");
    setLoading(true);
    setTimeout(() => {
      const aiMsg: Message = {
        id: (Date.now()+1).toString(), role:"ai",
        text: AI_RESPONSES["default"],
        time: new Date().toLocaleTimeString("bg-BG",{hour:"2-digit",minute:"2-digit"}),
      };
      setMessages(prev => [...prev, aiMsg]);
      setLoading(false);
    }, 1200);
  };

  const formatText = (t: string) =>
    t.split("\n").map((line, i) => {
      const parts = line.split(/\*\*(.*?)\*\*/g);
      return (
        <p key={i} className={line === "" ? "mt-2" : ""}>{
          parts.map((p, j) => j%2===1 ? <strong key={j}>{p}</strong> : p)
        }</p>
      );
    });

  return (
    <div className="flex flex-col h-full">
      {/* Header */}
      <div className="px-5 py-4 border-b border-gray-100 bg-white flex items-center gap-3">
        <div className="size-10 rounded-2xl bg-gradient-to-br from-blue-600 to-teal-500 flex items-center justify-center shadow-md shadow-blue-200">
          <Sparkles className="size-5 text-white" />
        </div>
        <div>
          <p className="text-sm text-gray-800">ZENITH AI РђСЃРёСЃС‚РµРЅС‚</p>
          <div className="flex items-center gap-1.5">
            <span className="size-1.5 rounded-full bg-emerald-500 animate-pulse" />
            <p className="text-xs text-gray-400">РђРєС‚РёРІРµРЅ В· РћРїС‚РёРјРёР·РёСЂР°РЅ Р·Р° СЃС‚СЂРѕРёС‚РµР»СЃС‚РІРѕ</p>
          </div>
        </div>
        <div className="ml-auto flex items-center gap-1.5 px-3 py-1 rounded-full bg-amber-50 border border-amber-200">
          <Zap className="size-3 text-amber-500" />
          <span className="text-xs text-amber-700">PRO РјРѕРґРµР»</span>
        </div>
      </div>

      {/* Messages */}
      <div className="flex-1 overflow-y-auto px-5 py-4 space-y-4 bg-gray-50">
        {/* Quick prompts */}
        {messages.length === 1 && (
          <div className="grid grid-cols-1 sm:grid-cols-2 gap-2">
            {QUICK_PROMPTS.map(p => (
              <button key={p} onClick={() => send(p)}
                className="text-left px-4 py-3 rounded-xl bg-white border border-gray-100 text-sm text-gray-600 hover:border-blue-300 hover:text-blue-700 hover:bg-blue-50 transition-all">
                {p}
              </button>
            ))}
          </div>
        )}

        {messages.map(msg => (
          <div key={msg.id} className={`flex gap-3 ${msg.role==="user" ? "justify-end" : "justify-start"}`}>
            {msg.role === "ai" && (
              <div className="size-8 rounded-2xl bg-gradient-to-br from-blue-600 to-teal-500 flex items-center justify-center flex-shrink-0 mt-1 shadow-md shadow-blue-200">
                <Bot className="size-4 text-white" />
              </div>
            )}
            <div className={`max-w-xl ${msg.role==="user" ? "order-first" : ""}`}>
              <div className={`px-4 py-3 rounded-2xl text-sm leading-relaxed space-y-0.5 ${
                msg.role==="user"
                  ? "bg-gradient-to-br from-blue-600 to-teal-600 text-white rounded-br-sm"
                  : "bg-white text-gray-700 rounded-bl-sm shadow-sm border border-gray-100"
              }`}>
                {formatText(msg.text)}
              </div>
              <div className={`flex items-center gap-2 mt-1 ${msg.role==="user" ? "justify-end" : "justify-start"}`}>
                <span className="text-[10px] text-gray-400">{msg.time}</span>
                {msg.role==="ai" && (
                  <>
                    <button className="size-5 flex items-center justify-center text-gray-300 hover:text-blue-500 transition-colors"><Copy className="size-3" /></button>
                    <button className="size-5 flex items-center justify-center text-gray-300 hover:text-emerald-500 transition-colors"><ThumbsUp className="size-3" /></button>
                    <button className="size-5 flex items-center justify-center text-gray-300 hover:text-red-500 transition-colors"><ThumbsDown className="size-3" /></button>
                  </>
                )}
              </div>
            </div>
            {msg.role === "user" && (
              <div className="size-8 rounded-2xl bg-gradient-to-br from-violet-500 to-blue-600 flex items-center justify-center flex-shrink-0 mt-1 text-white text-xs">
                РЎРЎ
              </div>
            )}
          </div>
        ))}

        {loading && (
          <div className="flex gap-3">
            <div className="size-8 rounded-2xl bg-gradient-to-br from-blue-600 to-teal-500 flex items-center justify-center flex-shrink-0 shadow-md shadow-blue-200">
              <Bot className="size-4 text-white" />
            </div>
            <div className="bg-white rounded-2xl rounded-bl-sm px-4 py-3 shadow-sm border border-gray-100">
              <div className="flex gap-1.5">
                {[0,1,2].map(i => (
                  <div key={i} className="size-2 rounded-full bg-blue-400 animate-bounce" style={{ animationDelay:`${i*0.15}s` }} />
                ))}
              </div>
            </div>
          </div>
        )}
        <div ref={endRef} />
      </div>

      {/* Input */}
      <div className="px-5 py-4 bg-white border-t border-gray-100">
        <div className="flex items-center gap-2 bg-gray-50 rounded-2xl border border-gray-200 px-4 py-2 focus-within:ring-2 focus-within:ring-blue-500/20 focus-within:border-blue-400 transition-all">
          <button className="text-gray-400 hover:text-gray-600 transition-colors flex-shrink-0"><Paperclip className="size-4" /></button>
          <input value={input} onChange={e=>setInput(e.target.value)} onKeyDown={e=>e.key==="Enter"&&!e.shiftKey&&send()}
            placeholder="Р—Р°РґР°Р№ РІСЉРїСЂРѕСЃ Р·Р° СЃС‚СЂРѕРёС‚РµР»РЅРёСЏ С‚Рё Р±РёР·РЅРµСЃ..."
            className="flex-1 bg-transparent text-sm text-gray-700 placeholder-gray-400 focus:outline-none" />
          <button className="text-gray-400 hover:text-gray-600 transition-colors flex-shrink-0"><Mic className="size-4" /></button>
          <button onClick={() => send()} disabled={!input.trim()||loading}
            className="size-8 flex items-center justify-center rounded-xl bg-gradient-to-br from-blue-600 to-teal-600 text-white hover:from-blue-700 hover:to-teal-700 transition-all active:scale-95 flex-shrink-0 shadow-sm disabled:opacity-50 disabled:cursor-not-allowed">
            <Send className="size-3.5" />
          </button>
        </div>
        <p className="text-center text-[10px] text-gray-400 mt-2">ZENITH AI РјРѕР¶Рµ РґР° РїСЂР°РІРё РіСЂРµС€РєРё. РљРѕРЅСЃСѓР»С‚РёСЂР°Р№С‚Рµ СЃРµ СЃ РµРєСЃРїРµСЂС‚ Р·Р° РїСЂР°РІРЅРё Рё С„РёРЅР°РЅСЃРѕРІРё СЂРµС€РµРЅРёСЏ.</p>
      </div>
    </div>
  );
}



// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ
// FILE: src/app/pages/pro/tools/ProAIStatsPage.tsx
// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ

import {
  BarChart, Bar, XAxis, YAxis, CartesianGrid, Tooltip,
  ResponsiveContainer, LineChart, Line, PieChart, Pie, Cell, Legend,
} from "recharts";
import { Sparkles, TrendingUp, TrendingDown, Brain, Zap } from "lucide-react";

const MONTHLY = [
  { month:"РћРєС‚",  revenue:68000, expenses:42000, profit:26000 },
  { month:"РќРѕРµ",  revenue:75000, expenses:45000, profit:30000 },
  { month:"Р”РµРє",  revenue:82000, expenses:48000, profit:34000 },
  { month:"РЇРЅ",   revenue:71000, expenses:43000, profit:28000 },
  { month:"Р¤РµРІ",  revenue:79000, expenses:46000, profit:33000 },
  { month:"РњР°СЂС‚", revenue:95000, expenses:52000, profit:43000 },
  { month:"РђРїСЂ",  revenue:88000, expenses:49000, profit:39000 },
];

const AI_USAGE = [
  { week:"РЎ1", contracts:12, kss:8, advice:24, docs:15 },
  { week:"РЎ2", contracts:15, kss:11, advice:30, docs:18 },
  { week:"РЎ3", contracts:9,  kss:14, advice:22, docs:12 },
  { week:"РЎ4", contracts:18, kss:16, advice:35, docs:22 },
];

const PIE_DATA = [
  { name:"Р”РѕРіРѕРІРѕСЂРё",    value:28, color:"#2563EB" },
  { name:"РљРЎРЎ",        value:22, color:"#0D9488" },
  { name:"AI РЎСЉРІРµС‚Рё",  value:35, color:"#8b5cf6" },
  { name:"Р”РѕРєСѓРјРµРЅС‚Рё",  value:15, color:"#f59e0b" },
];

const PREDICTIONS = [
  { label:"РџСЂРёС…РѕРґРё СЃР»РµРґРІР°С‰ РјРµСЃРµС†",  value:"92 000 Р»РІ",  change:"+4.5%",  up:true  },
  { label:"Р Р°Р·С…РѕРґРё СЃР»РµРґРІР°С‰ РјРµСЃРµС†",  value:"51 000 Р»РІ",  change:"+4.1%",  up:false },
  { label:"РќРѕРІРё Р·Р°РїРёС‚РІР°РЅРёСЏ",        value:"8-12",       change:"+20%",   up:true  },
  { label:"РџСЂРѕС†РµРЅС‚ СЃРїРµС‡РµР»РµРЅРё",      value:"68%",        change:"+3%",    up:true  },
];

const FMTR = (v: number) => `${(v/1000).toFixed(0)}Рє`;

export function ProAIStatsPage() {
  return (
    <div className="p-5 lg:p-7 space-y-6">
      {/* Header */}
      <div className="flex items-center gap-3">
        <div className="size-10 rounded-2xl bg-gradient-to-br from-violet-600 to-blue-600 flex items-center justify-center shadow-md shadow-violet-200">
          <Brain className="size-5 text-white" />
        </div>
        <div>
          <h1 className="text-xl text-gray-800">AI РЎС‚Р°С‚РёСЃС‚РёРєР°</h1>
          <p className="text-sm text-gray-500">РђРЅР°Р»РёР· РЅР° AI РёР·РїРѕР»Р·РІР°РЅРµ Рё Р±РёР·РЅРµСЃ РїСЂРµРґРёРєС†РёРё</p>
        </div>
      </div>

      {/* AI Predictions */}
      <div>
        <div className="flex items-center gap-2 mb-3">
          <Sparkles className="size-4 text-violet-600" />
          <p className="text-sm text-gray-700">AI РџСЂРµРґСЃРєР°Р·Р°РЅРёСЏ вЂ” РњР°Р№ 2026</p>
        </div>
        <div className="grid grid-cols-2 lg:grid-cols-4 gap-4">
          {PREDICTIONS.map(p => (
            <div key={p.label} className="bg-white rounded-2xl border border-gray-100 p-4">
              <p className="text-xl text-gray-800">{p.value}</p>
              <div className="flex items-center gap-1 mt-1">
                {p.up
                  ? <TrendingUp className="size-3.5 text-emerald-500" />
                  : <TrendingDown className="size-3.5 text-red-500" />
                }
                <span className={`text-xs ${p.up ? "text-emerald-600" : "text-red-600"}`}>{p.change}</span>
              </div>
              <p className="text-xs text-gray-400 mt-1">{p.label}</p>
            </div>
          ))}
        </div>
      </div>

      {/* Revenue chart */}
      <div className="bg-white rounded-2xl border border-gray-100 p-5">
        <p className="text-sm text-gray-700 mb-4">РџСЂРёС…РѕРґРё vs Р Р°Р·С…РѕРґРё (РїРѕСЃР»РµРґРЅРёС‚Рµ 7 РјРµСЃРµС†Р°)</p>
        <ResponsiveContainer width="100%" height={220}>
          <BarChart data={MONTHLY} barGap={4}>
            <CartesianGrid strokeDasharray="3 3" stroke="#f0f0f0" />
            <XAxis dataKey="month" tick={{ fontSize:11, fill:"#9ca3af" }} axisLine={false} tickLine={false} />
            <YAxis tick={{ fontSize:11, fill:"#9ca3af" }} axisLine={false} tickLine={false} tickFormatter={FMTR} />
            <Tooltip formatter={(v: number) => `${v.toLocaleString("bg-BG")} Р»РІ`} />
            <Bar dataKey="revenue"  name="РџСЂРёС…РѕРґРё" fill="#2563EB" radius={[4,4,0,0]} />
            <Bar dataKey="expenses" name="Р Р°Р·С…РѕРґРё" fill="#e5e7eb" radius={[4,4,0,0]} />
            <Bar dataKey="profit"   name="РџРµС‡Р°Р»Р±Р°" fill="#0D9488" radius={[4,4,0,0]} />
          </BarChart>
        </ResponsiveContainer>
      </div>

      <div className="grid grid-cols-1 lg:grid-cols-2 gap-5">
        {/* AI usage line chart */}
        <div className="bg-white rounded-2xl border border-gray-100 p-5">
          <div className="flex items-center gap-2 mb-4">
            <Zap className="size-4 text-blue-600" />
            <p className="text-sm text-gray-700">AI РёР·РїРѕР»Р·РІР°РЅРµ РїРѕ СЃРµРґРјРёС†Рё (Р±СЂРѕСЏ Р·Р°СЏРІРєРё)</p>
          </div>
          <ResponsiveContainer width="100%" height={200}>
            <LineChart data={AI_USAGE}>
              <CartesianGrid strokeDasharray="3 3" stroke="#f0f0f0" />
              <XAxis dataKey="week" tick={{ fontSize:11, fill:"#9ca3af" }} axisLine={false} tickLine={false} />
              <YAxis tick={{ fontSize:11, fill:"#9ca3af" }} axisLine={false} tickLine={false} />
              <Tooltip />
              <Line type="monotone" dataKey="contracts" name="Р”РѕРіРѕРІРѕСЂРё" stroke="#2563EB" strokeWidth={2} dot={{ r:3 }} />
              <Line type="monotone" dataKey="kss"       name="РљРЎРЎ"      stroke="#0D9488" strokeWidth={2} dot={{ r:3 }} />
              <Line type="monotone" dataKey="advice"    name="РЎСЉРІРµС‚Рё"   stroke="#8b5cf6" strokeWidth={2} dot={{ r:3 }} />
              <Line type="monotone" dataKey="docs"      name="Р”РѕРєСѓРјРµРЅС‚Рё"stroke="#f59e0b" strokeWidth={2} dot={{ r:3 }} />
            </LineChart>
          </ResponsiveContainer>
        </div>

        {/* Pie chart */}
        <div className="bg-white rounded-2xl border border-gray-100 p-5">
          <p className="text-sm text-gray-700 mb-4">Р Р°Р·РїСЂРµРґРµР»РµРЅРёРµ РЅР° AI С„СѓРЅРєС†РёРё</p>
          <div className="flex items-center gap-4">
            <ResponsiveContainer width="100%" height={200}>
              <PieChart>
                <Pie data={PIE_DATA} cx="50%" cy="50%" innerRadius={55} outerRadius={85} paddingAngle={3} dataKey="value">
                  {PIE_DATA.map((entry, i) => <Cell key={i} fill={entry.color} />)}
                </Pie>
                <Legend iconType="circle" iconSize={8} formatter={(v) => <span className="text-xs text-gray-600">{v}</span>} />
                <Tooltip formatter={(v: number) => `${v}%`} />
              </PieChart>
            </ResponsiveContainer>
          </div>
        </div>
      </div>

      {/* AI insight */}
      <div className="bg-gradient-to-r from-violet-50 to-blue-50 rounded-2xl border border-violet-100 p-5">
        <div className="flex items-center gap-2 mb-2">
          <Brain className="size-4 text-violet-600" />
          <p className="text-sm text-gray-700">AI РђРЅР°Р»РёР· РЅР° С‚СЂРµРЅРґР°</p>
        </div>
        <p className="text-sm text-gray-600 leading-relaxed">
          Р¤РёСЂРјР°С‚Р° РїРѕРєР°Р·РІР° <strong>СЃС‚Р°Р±РёР»РµРЅ СЂСЉСЃС‚ РѕС‚ 8-12% РјРµСЃРµС‡РЅРѕ</strong> Р·Р° РїРѕСЃР»РµРґРЅРѕС‚Рѕ С‚СЂРёРјРµСЃРµС‡РёРµ. РќР°Р№-РіРѕР»СЏРјРѕ РІР»РёСЏРЅРёРµ РёРјР° Р°РІС‚РѕРјР°С‚РёР·Р°С†РёСЏС‚Р° РЅР° РљРЎРЎ Рё РґРѕРіРѕРІРѕСЂРёС‚Рµ вЂ” СЃРїРµСЃС‚РµРЅРё СЃСЂРµРґРЅРѕ <strong>14 С‡Р°СЃР°/РјРµСЃРµС†</strong>. РџСЂРµРїРѕСЂСЉС‡РІР°Рј РґР° СѓРІРµР»РёС‡РёС‚Рµ РёР·РїРѕР»Р·РІР°РЅРµС‚Рѕ РЅР° AI РЎСЉРІРµС‚Рё вЂ” РїРѕРЅР°СЃС‚РѕСЏС‰РµРј РїРѕРґ-РёР·РїРѕР»Р·РІР°РЅР° С„СѓРЅРєС†РёСЏ СЃ РІРёСЃРѕРє РїРѕС‚РµРЅС†РёР°Р» Р·Р° РѕРїС‚РёРјРёР·Р°С†РёСЏ РЅР° С†РµРЅРѕРѕР±СЂР°Р·СѓРІР°РЅРµС‚Рѕ.
        </p>
      </div>
    </div>
  );
}



// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ
// FILE: src/app/pages/ClientDashboard.tsx
// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ

import { useState } from "react";
import { Link, useNavigate } from "react-router";
import {
  Wand2, Play, ArrowRight, Star, CheckCircle2,
  Clock, Sparkles, ChevronRight, MessageSquare,
  TrendingUp, Zap, ShieldCheck, Bot,
  Plus, Eye, Heart,
} from "lucide-react";

// в”Ђв”Ђв”Ђ Images в”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђ
const IMG = {
  bathroom:    "https://images.unsplash.com/photo-1612153284972-7e80a48abcb9?crop=entropy&cs=tinysrgb&fit=max&fm=jpg&w=800&q=80",
  kitchen:     "https://images.unsplash.com/photo-1771862956702-4e8b247e28b5?crop=entropy&cs=tinysrgb&fit=max&fm=jpg&w=800&q=80",
  worker:      "https://images.unsplash.com/photo-1627660080110-20045fd3875d?crop=entropy&cs=tinysrgb&fit=max&fm=jpg&w=800&q=80",
  living:      "https://images.unsplash.com/photo-1760072513442-9872656c1b07?crop=entropy&cs=tinysrgb&fit=max&fm=jpg&w=800&q=80",
  flooring:    "https://images.unsplash.com/photo-1636200534256-c08268363482?crop=entropy&cs=tinysrgb&fit=max&fm=jpg&w=800&q=80",
  contractor:  "https://images.unsplash.com/photo-1765648580890-732fa6d769c5?crop=entropy&cs=tinysrgb&fit=max&fm=jpg&w=400&q=80",
  bedroom:     "https://images.unsplash.com/photo-1649719742478-830ba2e55b5d?crop=entropy&cs=tinysrgb&fit=max&fm=jpg&w=800&q=80",
};

// в”Ђв”Ђв”Ђ Data в”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђ
const MY_PROJECTS = [
  {
    id: 1,
    name: "Р РµРјРѕРЅС‚ Р±Р°РЅСЏ вЂ” СѓР». Р’РёС‚РѕС€Р° 12",
    type: "Р‘Р°РЅСЏ",
    status: "active",
    progress: 65,
    budget: "4 200 Р»РІ",
    img: IMG.bathroom,
    contractor: "Р“РµРѕСЂРіРё РЎС‚СЂРѕРµРІ",
    eta: "12 Р°РїСЂ",
  },
  {
    id: 2,
    name: "Р‘РѕСЏРґРёСЃРІР°РЅРµ С…РѕР» + РєСѓС…РЅСЏ",
    type: "Р‘РѕСЏРґРёСЃРІР°РЅРµ",
    status: "pending",
    progress: 20,
    budget: "1 800 Р»РІ",
    img: IMG.living,
    contractor: "Р§Р°РєР° РѕС„РµСЂС‚Р°",
    eta: "вЂ“",
  },
];

const ZCLIPS = [
  { id: 1, title: "Р РµРјРѕРЅС‚ РЅР° Р±Р°РЅСЏ Р·Р° 10 РґРЅРё", views: "12.4K", likes: "843", duration: "3:24", img: IMG.bathroom, tag: "Р‘Р°РЅСЏ" },
  { id: 2, title: "РљСѓС…РЅСЏ РѕС‚ РЅСѓР»Р°С‚Р° вЂ” РїСЂРµРґРё Рё СЃР»РµРґ", views: "8.7K",  likes: "621", duration: "5:11", img: IMG.kitchen, tag: "РљСѓС…РЅСЏ" },
  { id: 3, title: "РџРѕСЃС‚Р°РІСЏРЅРµ РЅР° Р»Р°РјРёРЅРёСЂР°РЅ РїР°СЂРєРµС‚", views: "5.2K",  likes: "398", duration: "2:47", img: IMG.flooring, tag: "РџРѕРґРѕРІРё" },
];

const PROS = [
  { name: "Р“РµРѕСЂРіРё РЎС‚СЂРѕРµРІ", specialty: "Р’РёРљ & Р‘Р°РЅСЏ", rating: 4.9, jobs: 127, img: IMG.contractor, badge: "РўРѕРї РёР·РїСЉР»РЅРёС‚РµР»" },
  { name: "РњР°СЂС‚РёРЅ Р”РёРјРёС‚СЂРѕРІ", specialty: "РЎС‚СЂРѕРёС‚РµР»СЃС‚РІРѕ", rating: 4.8, jobs: 89,  img: IMG.worker,     badge: "РџСЂРѕРІРµСЂРµРЅ" },
];

const INSPIRATION = [
  { img: IMG.kitchen,  label: "РњРѕРґРµСЂРЅР° РєСѓС…РЅСЏ",    price: "РѕС‚ 8 500 Р»РІ" },
  { img: IMG.bedroom,  label: "РЈСЋС‚РЅР° СЃРїР°Р»РЅСЏ",     price: "РѕС‚ 3 200 Р»РІ" },
  { img: IMG.bathroom, label: "SPA Р±Р°РЅСЏ",         price: "РѕС‚ 5 800 Р»РІ" },
  { img: IMG.living,   label: "РћС‚РєСЂРёС‚ С…РѕР»",       price: "РѕС‚ 4 100 Р»РІ" },
];

const STATUS_STYLE: Record<string, { label: string; cls: string; dot: string }> = {
  active:  { label: "Р’ С…РѕРґ",       cls: "bg-blue-50 text-blue-700 border-blue-100",   dot: "bg-blue-500" },
  pending: { label: "Р§Р°РєР° РѕС„РµСЂС‚Р°", cls: "bg-amber-50 text-amber-700 border-amber-100", dot: "bg-amber-400" },
  done:    { label: "Р—Р°РІСЉСЂС€РµРЅ",    cls: "bg-green-50 text-green-700 border-green-100", dot: "bg-green-500" },
};

// в”Ђв”Ђв”Ђ Video Card в”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђ
function ZclipCard({ clip }: { clip: typeof ZCLIPS[0] }) {
  const [playing, setPlaying] = useState(false);
  return (
    <div className="group relative rounded-2xl overflow-hidden shadow-md cursor-pointer flex-shrink-0 w-56 sm:w-64"
      onClick={() => setPlaying(!playing)}>
      <img src={clip.img} alt={clip.title} className="w-full h-40 object-cover group-hover:scale-105 transition-transform duration-500" />
      {/* Gradient overlay */}
      <div className="absolute inset-0 bg-gradient-to-t from-black/75 via-black/20 to-transparent" />
      {/* Tag */}
      <div className="absolute top-3 left-3">
        <span className="px-2 py-0.5 rounded-full bg-white/20 backdrop-blur-sm text-white text-xs border border-white/20">
          {clip.tag}
        </span>
      </div>
      {/* Duration */}
      <div className="absolute top-3 right-3">
        <span className="px-2 py-0.5 rounded-md bg-black/50 text-white text-xs">{clip.duration}</span>
      </div>
      {/* Play button */}
      <div className="absolute inset-0 flex items-center justify-center">
        <div className={`size-12 rounded-full flex items-center justify-center transition-all duration-200 ${playing ? "bg-white scale-110" : "bg-white/25 backdrop-blur-sm group-hover:bg-white/40 group-hover:scale-110"}`}>
          <Play className={`size-5 ml-0.5 ${playing ? "text-blue-600" : "text-white"}`} fill="currentColor" />
        </div>
      </div>
      {/* Bottom info */}
      <div className="absolute bottom-0 left-0 right-0 p-3">
        <p className="text-white text-sm leading-snug mb-1.5 line-clamp-2">{clip.title}</p>
        <div className="flex items-center gap-3 text-white/70 text-xs">
          <span className="flex items-center gap-1"><Eye className="size-3" />{clip.views}</span>
          <span className="flex items-center gap-1"><Heart className="size-3" />{clip.likes}</span>
        </div>
      </div>
    </div>
  );
}

// в”Ђв”Ђв”Ђ Main Dashboard в”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђв”Ђ
export function ClientDashboard() {
  const navigate = useNavigate();

  return (
    <div className="pb-16">

      {/* в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ
          1. HERO WELCOME BANNER
      в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ */}
      <div className="relative overflow-hidden bg-gradient-to-r from-blue-600 via-blue-700 to-teal-600 px-6 pt-8 pb-10 lg:px-10">
        {/* Decorative blobs */}
        <div className="absolute -top-10 -right-10 size-64 bg-white/5 rounded-full blur-3xl pointer-events-none" />
        <div className="absolute bottom-0 left-1/3 size-48 bg-teal-300/10 rounded-full blur-3xl pointer-events-none" />
        {/* Grid pattern */}
        <svg className="absolute inset-0 w-full h-full opacity-[0.06] pointer-events-none" xmlns="http://www.w3.org/2000/svg">
          <defs>
            <pattern id="dash-grid" width="32" height="32" patternUnits="userSpaceOnUse">
              <path d="M 32 0 L 0 0 0 32" fill="none" stroke="white" strokeWidth="0.6" />
            </pattern>
          </defs>
          <rect width="100%" height="100%" fill="url(#dash-grid)" />
        </svg>

        <div className="relative z-10 flex flex-col sm:flex-row sm:items-center sm:justify-between gap-6">
          <div>
            {/* AI badge */}
            <div className="inline-flex items-center gap-1.5 px-3 py-1 rounded-full bg-white/15 border border-white/20 mb-3">
              <Bot className="size-3.5 text-teal-200" />
              <span className="text-xs text-white/90">ZENITH AI Рµ РѕРЅР»Р°Р№РЅ</span>
              <span className="size-1.5 rounded-full bg-teal-300 animate-pulse" />
            </div>
            <h1 className="text-2xl sm:text-3xl text-white mb-2 leading-tight">
              Р”РѕР±СЂРµ РґРѕС€Р»Рё, РРІР°РЅ! рџ‘‹
            </h1>
            <p className="text-blue-100 text-sm max-w-sm leading-relaxed">
              РРјР°С‚Рµ <span className="text-white font-medium">2 Р°РєС‚РёРІРЅРё РїСЂРѕРµРєС‚Р°</span>. ZENITH AI Рµ РіРѕС‚РѕРІ РґР° РІРё РїРѕРјРѕРіРЅРµ СЃ РІСЃРёС‡РєРѕ вЂ” РѕС‚ РѕС„РµСЂС‚Рё РґРѕ РґРѕРіРѕРІРѕСЂРё.
            </p>
          </div>

          {/* Stats pills */}
          <div className="flex sm:flex-col gap-3">
            {[
              { icon: TrendingUp, v: "2",    l: "РђРєС‚РёРІРЅРё",   c: "text-blue-200" },
              { icon: Clock,      v: "1",    l: "Р§Р°РєР°С‰Рё",    c: "text-amber-200" },
              { icon: CheckCircle2, v: "5",  l: "Р—Р°РІСЉСЂС€РµРЅРё", c: "text-teal-200" },
            ].map((s, i) => (
              <div key={i} className="flex items-center gap-2 px-3 py-2 rounded-xl bg-white/10 backdrop-blur-sm border border-white/15">
                <s.icon className={`size-4 ${s.c}`} />
                <span className="text-white font-semibold">{s.v}</span>
                <span className="text-white/60 text-xs">{s.l}</span>
              </div>
            ))}
          </div>
        </div>

        {/* Quick action row */}
        <div className="relative z-10 flex gap-3 mt-6 flex-wrap">
          <button
            onClick={() => navigate("/client/project-wizard")}
            className="flex items-center gap-2 px-4 py-2.5 rounded-xl bg-white text-blue-700 text-sm shadow-lg hover:shadow-xl hover:scale-[1.02] transition-all active:scale-95"
          >
            <Wand2 className="size-4" />
            РЎС‚Р°СЂС‚РёСЂР°Р№ РЅРѕРІ РїСЂРѕРµРєС‚
          </button>
          <button
            onClick={() => navigate("/client/chat")}
            className="flex items-center gap-2 px-4 py-2.5 rounded-xl bg-white/15 border border-white/25 text-white text-sm hover:bg-white/25 transition-all"
          >
            <MessageSquare className="size-4" />
            Р§Р°С‚РѕРІРµ
          </button>
        </div>
      </div>


      {/* в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ
          2. ZENITH AI TEASER
      в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ */}
      <div className="px-5 lg:px-8 mt-6">
        <div className="relative overflow-hidden rounded-2xl border border-blue-100 bg-gradient-to-r from-blue-50 via-white to-teal-50 p-5">
          <div className="absolute right-0 top-0 bottom-0 w-32 bg-gradient-to-l from-teal-50 to-transparent pointer-events-none" />
          <div className="flex items-start gap-4 relative z-10">
            <div className="size-11 rounded-2xl bg-gradient-to-br from-blue-600 to-teal-500 flex items-center justify-center flex-shrink-0 shadow-md shadow-blue-200">
              <Sparkles className="size-5 text-white" />
            </div>
            <div className="flex-1 min-w-0">
              <div className="flex items-center gap-2 mb-1">
                <p className="text-gray-900 text-sm">ZENITH AI РђСЃРёСЃС‚РµРЅС‚</p>
                <span className="px-2 py-0.5 rounded-full bg-blue-100 text-blue-700 text-xs">PRO С„СѓРЅРєС†РёСЏ</span>
              </div>
              <p className="text-gray-500 text-xs leading-relaxed mb-3">
                вЂћРРІР°РЅРµ, РїСЂРѕРµРєС‚СЉС‚ РІРё Р·Р° Р±Р°РЅСЏ Рµ РЅР° 65%. РџСЂРµРїРѕСЂСЉС‡РІР°Рј РґР° РїРѕРёСЃРєР°С‚Рµ С„РёРЅР°Р»РµРЅ РѕРіР»РµРґ РѕС‚ Р“РµРѕСЂРіРё РїСЂРµРґРё РїР»Р°С‰Р°РЅРµС‚Рѕ."
              </p>
              <div className="flex flex-wrap gap-2">
                {["Р“РµРЅРµСЂРёСЂР°Р№ РґРѕРіРѕРІРѕСЂ", "РџРѕРїРёС‚Р°Р№ Р·Р° С†РµРЅРё", "РђРЅР°Р»РёР·РёСЂР°Р№ РѕС„РµСЂС‚Р°"].map((q) => (
                  <button key={q} className="px-3 py-1.5 rounded-xl bg-white border border-blue-200 text-blue-700 text-xs hover:bg-blue-50 hover:border-blue-300 transition-all shadow-sm">
                    {q}
                  </button>
                ))}
              </div>
            </div>
          </div>
        </div>
      </div>


      {/* в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ
          3. РњРћР РџР РћР•РљРўР вЂ” visual cards
      в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ */}
      <div className="px-5 lg:px-8 mt-8">
        <div className="flex items-center justify-between mb-4">
          <h2 className="text-gray-800">РњРѕРёС‚Рµ РїСЂРѕРµРєС‚Рё</h2>
          <Link to="/client/projects" className="flex items-center gap-1 text-xs text-blue-600 hover:text-blue-700">
            Р’СЃРёС‡РєРё <ArrowRight className="size-3" />
          </Link>
        </div>

        <div className="grid grid-cols-1 sm:grid-cols-2 gap-4">
          {MY_PROJECTS.map((p) => {
            const s = STATUS_STYLE[p.status];
            return (
              <div key={p.id} className="group bg-white rounded-2xl border border-gray-100 overflow-hidden shadow-sm hover:shadow-lg transition-all duration-300 cursor-pointer">
                {/* Image */}
                <div className="relative h-44 overflow-hidden">
                  <img src={p.img} alt={p.name} className="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500" />
                  <div className="absolute inset-0 bg-gradient-to-t from-black/60 to-transparent" />
                  {/* Status */}
                  <div className="absolute top-3 left-3">
                    <span className={`flex items-center gap-1.5 px-2.5 py-1 rounded-full text-xs border backdrop-blur-sm bg-white/90 ${s.cls}`}>
                      <span className={`size-1.5 rounded-full ${s.dot}`} />
                      {s.label}
                    </span>
                  </div>
                  {/* Budget */}
                  <div className="absolute top-3 right-3">
                    <span className="px-2.5 py-1 rounded-full bg-black/40 backdrop-blur-sm text-white text-xs border border-white/20">
                      {p.budget}
                    </span>
                  </div>
                  {/* Bottom overlay */}
                  <div className="absolute bottom-3 left-3 right-3">
                    <p className="text-white text-sm leading-snug">{p.name}</p>
                  </div>
                </div>

                {/* Info */}
                <div className="p-4">
                  {/* Progress */}
                  <div className="mb-3">
                    <div className="flex items-center justify-between mb-1.5">
                      <span className="text-xs text-gray-500">РќР°РїСЂРµРґСЉРє</span>
                      <span className="text-xs text-blue-700 font-medium">{p.progress}%</span>
                    </div>
                    <div className="h-1.5 bg-gray-100 rounded-full overflow-hidden">
                      <div
                        className="h-full rounded-full bg-gradient-to-r from-blue-500 to-teal-500 transition-all"
                        style={{ width: `${p.progress}%` }}
                      />
                    </div>
                  </div>

                  <div className="flex items-center justify-between">
                    <div className="flex items-center gap-2">
                      <div className="size-6 rounded-full bg-gradient-to-br from-blue-400 to-teal-400 flex items-center justify-center text-white text-xs flex-shrink-0">
                        {p.contractor[0]}
                      </div>
                      <span className="text-xs text-gray-600">{p.contractor}</span>
                    </div>
                    <div className="flex items-center gap-1 text-xs text-gray-400">
                      <Clock className="size-3" />
                      {p.eta}
                    </div>
                  </div>
                </div>
              </div>
            );
          })}

          {/* + РќРѕРІ РїСЂРѕРµРєС‚ card */}
          <button
            onClick={() => navigate("/client/project-wizard")}
            className="group border-2 border-dashed border-gray-200 rounded-2xl p-6 flex flex-col items-center justify-center gap-3 hover:border-blue-300 hover:bg-blue-50/50 transition-all min-h-[200px]"
          >
            <div className="size-12 rounded-2xl bg-blue-50 group-hover:bg-blue-100 flex items-center justify-center transition-colors">
              <Plus className="size-6 text-blue-500" />
            </div>
            <div className="text-center">
              <p className="text-sm text-gray-700 group-hover:text-blue-700 transition-colors">РќРѕРІ РїСЂРѕРµРєС‚</p>
              <p className="text-xs text-gray-400 mt-0.5">ZENITH AI С‰Рµ РІРё РїРѕРјРѕРіРЅРµ</p>
            </div>
          </button>
        </div>
      </div>


      {/* в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ
          4. ZCLIPS вЂ” С…РѕСЂРёР·РѕРЅС‚Р°Р»РµРЅ СЃРєСЂРѕР»
      в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ */}
      <div className="mt-10">
        <div className="px-5 lg:px-8 flex items-center justify-between mb-4">
          <div className="flex items-center gap-2">
            <div className="size-6 rounded-lg bg-gradient-to-br from-blue-600 to-teal-500 flex items-center justify-center">
              <Play className="size-3 text-white ml-0.5" fill="white" />
            </div>
            <h2 className="text-gray-800">Zclips вЂ” СЂРµР°Р»РЅРё РїСЂРѕРµРєС‚Рё</h2>
          </div>
          <Link to="/community" className="flex items-center gap-1 text-xs text-blue-600 hover:text-blue-700">
            Р’РёР¶ РІСЃРёС‡РєРё <ArrowRight className="size-3" />
          </Link>
        </div>
        <p className="px-5 lg:px-8 text-xs text-gray-400 mb-4">
          Р’РёРґРµР° РѕС‚ СЂРµР°Р»РЅРё СЂРµРјРѕРЅС‚Рё вЂ” РІРґСЉС…РЅРѕРІРµС‚Рµ СЃРµ РїСЂРµРґРё РґР° СЃС‚Р°СЂС‚РёСЂР°С‚Рµ РІР°С€РёСЏ РїСЂРѕРµРєС‚
        </p>

        {/* Scrollable row */}
        <div className="flex gap-4 overflow-x-auto pb-3 px-5 lg:px-8 snap-x snap-mandatory scrollbar-none"
          style={{ scrollbarWidth: "none", msOverflowStyle: "none" }}>
          {ZCLIPS.map((clip) => (
            <div key={clip.id} className="snap-start">
              <ZclipCard clip={clip} />
            </div>
          ))}
          {/* "Р’РёР¶ РІСЃРёС‡РєРё" card */}
          <Link
            to="/community"
            className="snap-start flex-shrink-0 w-44 rounded-2xl border-2 border-dashed border-gray-200 flex flex-col items-center justify-center gap-2 h-40 hover:border-blue-300 hover:bg-blue-50/50 transition-all"
          >
            <div className="size-10 rounded-xl bg-blue-50 flex items-center justify-center">
              <Play className="size-5 text-blue-500 ml-0.5" />
            </div>
            <p className="text-xs text-gray-500 text-center px-2">Р’РёР¶ РІСЃРёС‡РєРё Zclips</p>
          </Link>
        </div>
      </div>


      {/* в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ
          5. РўРћРџ РР—РџРЄР›РќРРўР•Р›Р
      в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ */}
      <div className="px-5 lg:px-8 mt-10">
        <div className="flex items-center justify-between mb-4">
          <div>
            <h2 className="text-gray-800">РўРѕРї РёР·РїСЉР»РЅРёС‚РµР»Рё РІ СЂР°Р№РѕРЅР°</h2>
            <p className="text-xs text-gray-400 mt-0.5">РџСЂРѕРІРµСЂРµРЅРё РјР°Р№СЃС‚РѕСЂРё СЃ СЂРµР°Р»РЅРё РѕС‚Р·РёРІРё</p>
          </div>
          <Link to="/client/marketplace" className="flex items-center gap-1 text-xs text-blue-600 hover:text-blue-700">
            РџР°Р·Р°СЂ <ArrowRight className="size-3" />
          </Link>
        </div>

        <div className="grid grid-cols-1 sm:grid-cols-2 gap-4">
          {PROS.map((pro, i) => (
            <div key={i} className="group bg-white rounded-2xl border border-gray-100 p-4 flex items-center gap-4 shadow-sm hover:shadow-md hover:border-blue-100 transition-all cursor-pointer">
              <div className="relative flex-shrink-0">
                <img src={pro.img} alt={pro.name} className="size-14 rounded-2xl object-cover" />
                <span className="absolute -bottom-1 -right-1 size-4 rounded-full bg-green-400 border-2 border-white" />
              </div>
              <div className="flex-1 min-w-0">
                <div className="flex items-center gap-2 flex-wrap mb-0.5">
                  <p className="text-sm text-gray-800">{pro.name}</p>
                  <span className="px-1.5 py-0.5 rounded-md bg-teal-50 text-teal-700 text-xs border border-teal-100 flex items-center gap-1">
                    <ShieldCheck className="size-3" />{pro.badge}
                  </span>
                </div>
                <p className="text-xs text-gray-500 mb-1.5">{pro.specialty}</p>
                <div className="flex items-center gap-3 text-xs text-gray-500">
                  <span className="flex items-center gap-1 text-amber-500">
                    <Star className="size-3" fill="currentColor" />
                    {pro.rating}
                  </span>
                  <span>{pro.jobs} Р·Р°РІСЉСЂС€РµРЅРё</span>
                </div>
              </div>
              <button className="flex-shrink-0 px-3 py-2 rounded-xl bg-blue-50 text-blue-600 text-xs hover:bg-blue-100 transition-colors group-hover:bg-blue-600 group-hover:text-white">
                РџРѕСЂСЉС‡Р°Р№
              </button>
            </div>
          ))}
        </div>
      </div>


      {/* в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ
          6. Р’Р”РЄРҐРќРћР’Р•РќРР• вЂ” РіР°Р»РµСЂРёСЏ
      в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ */}
      <div className="px-5 lg:px-8 mt-10">
        <div className="mb-4">
          <h2 className="text-gray-800">РќР°РјРµСЂРµС‚Рµ РІРґСЉС…РЅРѕРІРµРЅРёРµ</h2>
          <p className="text-xs text-gray-400 mt-0.5">Р РµР°Р»РЅРё СЂРµР·СѓР»С‚Р°С‚Рё РѕС‚ РєР»РёРµРЅС‚Рё РЅР° TemaDom</p>
        </div>

        <div className="grid grid-cols-2 sm:grid-cols-4 gap-3">
          {INSPIRATION.map((item, i) => (
            <button
              key={i}
              onClick={() => navigate("/client/project-wizard")}
              className="group relative rounded-2xl overflow-hidden aspect-[3/4] shadow-sm hover:shadow-xl transition-all duration-300"
            >
              <img src={item.img} alt={item.label} className="w-full h-full object-cover group-hover:scale-110 transition-transform duration-500" />
              <div className="absolute inset-0 bg-gradient-to-t from-black/70 via-black/10 to-transparent" />
              <div className="absolute bottom-0 left-0 right-0 p-3">
                <p className="text-white text-xs leading-tight mb-1">{item.label}</p>
                <p className="text-teal-300 text-xs">{item.price}</p>
              </div>
              {/* Hover overlay */}
              <div className="absolute inset-0 flex items-center justify-center opacity-0 group-hover:opacity-100 transition-opacity">
                <div className="px-3 py-1.5 rounded-xl bg-white/90 text-blue-700 text-xs flex items-center gap-1 shadow-lg">
                  <Wand2 className="size-3" />
                  РЎС‚Р°СЂС‚РёСЂР°Р№
                </div>
              </div>
            </button>
          ))}
        </div>
      </div>


      {/* в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ
          7. Р—РђР©Рћ TEMADOM вЂ” trust bar
      в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ */}
      <div className="px-5 lg:px-8 mt-10">
        <div className="rounded-2xl bg-gradient-to-br from-gray-900 to-gray-800 p-6 relative overflow-hidden">
          <div className="absolute inset-0 pointer-events-none overflow-hidden opacity-10">
            <svg className="absolute inset-0 w-full h-full" xmlns="http://www.w3.org/2000/svg">
              <defs>
                <pattern id="trust-grid" width="24" height="24" patternUnits="userSpaceOnUse">
                  <path d="M 24 0 L 0 0 0 24" fill="none" stroke="white" strokeWidth="0.5" />
                </pattern>
              </defs>
              <rect width="100%" height="100%" fill="url(#trust-grid)" />
            </svg>
          </div>
          <div className="relative z-10">
            <div className="flex items-center gap-2 mb-3">
              <Zap className="size-4 text-teal-400" />
              <span className="text-teal-400 text-xs tracking-wider">Р—РђР©Рћ TEMADOM</span>
            </div>
            <p className="text-white text-lg mb-5 leading-snug max-w-sm">
              Р•РґРёРЅСЃС‚РІРµРЅРѕС‚Рѕ РјСЏСЃС‚Рѕ, РєСЉРґРµС‚Рѕ СЂРµРјРѕРЅС‚СЉС‚ РІСЉСЂРІРё РїРѕ РїР»Р°РЅ вЂ” СЃ AI РіР°СЂР°РЅС†РёСЏ.
            </p>
            <div className="grid grid-cols-3 gap-4 mb-5">
              {[
                { v: "500+", l: "Р”РѕРІРѕР»РЅРё РєР»РёРµРЅС‚Рё" },
                { v: "98%",  l: "Р’ СЃСЂРѕРє" },
                { v: "4.9в…", l: "РЎСЂРµРґРЅР° РѕС†РµРЅРєР°" },
              ].map((s, i) => (
                <div key={i}>
                  <p className="text-white text-lg">{s.v}</p>
                  <p className="text-gray-400 text-xs">{s.l}</p>
                </div>
              ))}
            </div>
            <button
              onClick={() => navigate("/client/project-wizard")}
              className="flex items-center gap-2 px-5 py-2.5 rounded-xl bg-gradient-to-r from-blue-500 to-teal-500 text-white text-sm hover:opacity-90 transition-opacity shadow-lg"
            >
              <Wand2 className="size-4" />
              РЎС‚Р°СЂС‚РёСЂР°Р№ Р±РµР·РїР»Р°С‚РЅРѕ
              <ChevronRight className="size-4" />
            </button>
          </div>
        </div>
      </div>

    </div>
  );
}



// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ
// FILE: src/app/pages/client/ProjectWizardPage.tsx
// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ

import { useState } from "react";
import { useNavigate } from "react-router";
import {
  Wand2, ChevronRight, ChevronLeft, Check,
  Bath, UtensilsCrossed, Sofa, Hammer, Zap, Droplets,
  PaintBucket, Building2, Sparkles, MapPin, Calendar,
  Banknote, FileText, Send, Home,
} from "lucide-react";

const PROJECT_TYPES = [
  { id: "bathroom", icon: Bath,            label: "Р‘Р°РЅСЏ",          desc: "Р РµРјРѕРЅС‚ / РѕР±Р»РёС†РѕРІРєР°" },
  { id: "kitchen",  icon: UtensilsCrossed, label: "РљСѓС…РЅСЏ",         desc: "РћР±Р·Р°РІРµР¶РґР°РЅРµ / СЂРµРјРѕРЅС‚" },
  { id: "living",   icon: Sofa,            label: "РҐРѕР» / СЃС‚Р°СЏ",    desc: "Р‘РѕСЏРґРёСЃРІР°РЅРµ / РїРѕРґРѕРІРµ" },
  { id: "repair",   icon: Hammer,          label: "РћР±С‰ СЂРµРјРѕРЅС‚",    desc: "Р¦СЏР»РѕСЃС‚РµРЅ СЂРµРјРѕРЅС‚" },
  { id: "electric", icon: Zap,             label: "Р•Р»РµРєС‚СЂРѕ",       desc: "РРЅСЃС‚Р°Р»Р°С†РёРё / С‚Р°Р±Р»Рѕ" },
  { id: "plumbing", icon: Droplets,        label: "Р’РёРљ",           desc: "РўСЂСЉР±Рё / С„РёС‚РёРЅРіРё" },
  { id: "painting", icon: PaintBucket,     label: "Р‘РѕСЏРґРёСЃРІР°РЅРµ",    desc: "Р’СЉС‚СЂРµС€РЅРѕ / С„Р°СЃР°РґР°" },
  { id: "building", icon: Building2,       label: "РЎС‚СЂРѕРёС‚РµР»СЃС‚РІРѕ",  desc: "Р—РёРґР°СЂРёСЏ / РєРѕРЅСЃС‚СЂСѓРєС†РёСЏ" },
];

const BUDGETS = [
  { id: "b1", label: "Р”Рѕ 2 000 Р»РІ",       range: "0-2000" },
  { id: "b2", label: "2 000 вЂ“ 5 000 Р»РІ",  range: "2000-5000" },
  { id: "b3", label: "5 000 вЂ“ 10 000 Р»РІ", range: "5000-10000" },
  { id: "b4", label: "10 000 вЂ“ 20 000 Р»РІ", range: "10000-20000" },
  { id: "b5", label: "РќР°Рґ 20 000 Р»РІ",     range: "20000+" },
];

const TIMELINES = [
  { id: "t1", label: "РЎРїРµС€РЅРѕ",      desc: "Р”Рѕ 2 СЃРµРґРјРёС†Рё" },
  { id: "t2", label: "РЎРєРѕСЂРѕ",       desc: "1 вЂ“ 3 РјРµСЃРµС†Р°" },
  { id: "t3", label: "РџР»Р°РЅРёСЂР°РЅРѕ",   desc: "3 вЂ“ 6 РјРµСЃРµС†Р°" },
  { id: "t4", label: "Р‘РµР· Р±СЉСЂР·Р°РЅРµ", desc: "РљРѕРіР°С‚Рѕ СЃРµ РЅР°РјРµСЂРё" },
];

const STEPS = ["РўРёРї", "Р”РµС‚Р°Р№Р»Рё", "Р‘СЋРґР¶РµС‚", "Р›РѕРєР°С†РёСЏ", "Р“РѕС‚РѕРІРѕ"];

export function ProjectWizardPage() {
  const navigate = useNavigate();
  const [step, setStep] = useState(0);
  const [form, setForm] = useState({
    type: "",
    description: "",
    area: "",
    budget: "",
    timeline: "",
    city: "",
    address: "",
    extras: [] as string[],
  });
  const [loading, setLoading] = useState(false);
  const [done, setDone] = useState(false);

  const canNext = () => {
    if (step === 0) return !!form.type;
    if (step === 1) return form.description.length >= 10;
    if (step === 2) return !!form.budget && !!form.timeline;
    if (step === 3) return !!form.city;
    return true;
  };

  const handleNext = () => {
    if (step === 3) {
      setLoading(true);
      setTimeout(() => { setLoading(false); setDone(true); setStep(4); }, 2000);
    } else setStep(s => s + 1);
  };

  const selectedType = PROJECT_TYPES.find(t => t.id === form.type);

  return (
    <div className="min-h-full bg-gray-50 flex flex-col">
      {/* Top bar */}
      <div className="bg-white border-b border-gray-100 px-5 lg:px-8 py-4">
        <div className="flex items-center gap-3 max-w-2xl mx-auto">
          <button onClick={() => navigate("/client")} className="size-9 flex items-center justify-center rounded-xl hover:bg-gray-100 text-gray-500 transition-colors">
            <Home className="size-4" />
          </button>
          <div className="flex-1">
            <h1 className="text-gray-800">РќРѕРІ РїСЂРѕРµРєС‚</h1>
            <p className="text-xs text-gray-400">ZENITH AI С‰Рµ РІРё РїРѕРјРѕРіРЅРµ СЃС‚СЉРїРєР° РїРѕ СЃС‚СЉРїРєР°</p>
          </div>
          <div className="flex items-center gap-1.5 px-3 py-1.5 rounded-full bg-blue-50 border border-blue-100">
            <Sparkles className="size-3.5 text-blue-500" />
            <span className="text-xs text-blue-700">AI Wizard</span>
          </div>
        </div>
      </div>

      <div className="flex-1 px-5 lg:px-8 py-8 max-w-2xl mx-auto w-full">
        {/* Progress */}
        <div className="flex items-center gap-1.5 mb-8">
          {STEPS.map((s, i) => (
            <div key={s} className="flex items-center gap-1.5 flex-1">
              <div className={`flex items-center justify-center size-7 rounded-full text-xs transition-all flex-shrink-0
                ${i < step ? "bg-teal-500 text-white" : i === step ? "bg-blue-600 text-white shadow-md shadow-blue-200" : "bg-gray-100 text-gray-400"}`}>
                {i < step ? <Check className="size-3.5" /> : i + 1}
              </div>
              {i < STEPS.length - 1 && (
                <div className={`flex-1 h-0.5 rounded-full transition-all ${i < step ? "bg-teal-400" : "bg-gray-200"}`} />
              )}
            </div>
          ))}
        </div>

        {/* в”Ђв”Ђ Step 0: РўРёРї в”Ђв”Ђ */}
        {step === 0 && (
          <div>
            <h2 className="text-gray-800 mb-1">РљР°РєСЉРІ РїСЂРѕРµРєС‚ РїР»Р°РЅРёСЂР°С‚Рµ?</h2>
            <p className="text-sm text-gray-400 mb-6">РР·Р±РµСЂРµС‚Рµ РєР°С‚РµРіРѕСЂРёСЏС‚Р°, Р·Р° РґР° РІРёРґРёС‚Рµ РїРѕРґС…РѕРґСЏС‰Рё РёР·РїСЉР»РЅРёС‚РµР»Рё</p>
            <div className="grid grid-cols-2 sm:grid-cols-4 gap-3">
              {PROJECT_TYPES.map(({ id, icon: Icon, label, desc }) => (
                <button key={id} onClick={() => setForm(f => ({ ...f, type: id }))}
                  className={`group p-4 rounded-2xl border-2 text-left transition-all hover:shadow-md
                    ${form.type === id ? "border-blue-500 bg-blue-50 shadow-md shadow-blue-100" : "border-gray-100 bg-white hover:border-blue-200"}`}>
                  <div className={`size-10 rounded-xl flex items-center justify-center mb-2.5 transition-colors
                    ${form.type === id ? "bg-blue-100" : "bg-gray-100 group-hover:bg-blue-50"}`}>
                    <Icon className={`size-5 ${form.type === id ? "text-blue-600" : "text-gray-500"}`} />
                  </div>
                  <p className={`text-sm mb-0.5 ${form.type === id ? "text-blue-700" : "text-gray-800"}`}>{label}</p>
                  <p className="text-xs text-gray-400">{desc}</p>
                  {form.type === id && (
                    <div className="mt-2 flex items-center gap-1 text-blue-600 text-xs">
                      <Check className="size-3" />РР·Р±СЂР°РЅРѕ
                    </div>
                  )}
                </button>
              ))}
            </div>
          </div>
        )}

        {/* в”Ђв”Ђ Step 1: Р”РµС‚Р°Р№Р»Рё в”Ђв”Ђ */}
        {step === 1 && (
          <div>
            <h2 className="text-gray-800 mb-1">РћРїРёС€РµС‚Рµ РїСЂРѕРµРєС‚Р°</h2>
            <p className="text-sm text-gray-400 mb-6">РљРѕР»РєРѕС‚Рѕ РїРѕРІРµС‡Рµ РґРµС‚Р°Р№Р»Рё, С‚РѕР»РєРѕРІР° РїРѕ-С‚РѕС‡РЅР° РѕС„РµСЂС‚Р° С‰Рµ РїРѕР»СѓС‡РёС‚Рµ</p>
            {selectedType && (
              <div className="flex items-center gap-2 px-3 py-2 bg-blue-50 rounded-xl border border-blue-100 mb-5">
                <selectedType.icon className="size-4 text-blue-600" />
                <span className="text-sm text-blue-700">{selectedType.label}</span>
              </div>
            )}
            <div className="space-y-4">
              <div>
                <label className="block text-sm text-gray-700 mb-2">РћРїРёСЃР°РЅРёРµ РЅР° РїСЂРѕРµРєС‚Р° *</label>
                <textarea rows={4} placeholder="РќР°РїСЂРёРјРµСЂ: РСЃРєР°Рј РґР° СЂРµРјРѕРЅС‚РёСЂР°Рј Р±Р°РЅСЏС‚Р° РЅР° РѕРєРѕР»Рѕ 6 РєРІ.Рј вЂ” СЃРјСЏРЅР° РЅР° РїР»РѕС‡РєРё, РјРёРІРєР°, Р±Р°РЅСЏ Рё Р’РёРљ РёРЅСЃС‚Р°Р»Р°С†РёСЏ..."
                  value={form.description} onChange={e => setForm(f => ({ ...f, description: e.target.value }))}
                  className="w-full px-4 py-3 bg-white border border-gray-200 rounded-xl text-sm text-gray-800 placeholder-gray-400 focus:outline-none focus:ring-2 focus:ring-blue-500/20 focus:border-blue-400 resize-none transition-all" />
                <div className="flex justify-between mt-1.5">
                  <p className="text-xs text-gray-400">РњРёРЅРёРјСѓРј 10 Р·РЅР°РєР°</p>
                  <p className={`text-xs ${form.description.length >= 10 ? "text-teal-500" : "text-gray-400"}`}>{form.description.length} Р·РЅР°РєР°</p>
                </div>
              </div>
              <div>
                <label className="block text-sm text-gray-700 mb-2">РџР»РѕС‰ (РєРІ.Рј) вЂ” РїРѕ Р¶РµР»Р°РЅРёРµ</label>
                <input type="number" placeholder="РќР°РїСЂ. 12" value={form.area} onChange={e => setForm(f => ({ ...f, area: e.target.value }))}
                  className="w-full px-4 py-3 bg-white border border-gray-200 rounded-xl text-sm text-gray-800 placeholder-gray-400 focus:outline-none focus:ring-2 focus:ring-blue-500/20 focus:border-blue-400 transition-all" />
              </div>
              <div>
                <label className="block text-sm text-gray-700 mb-2">Р”РѕРїСЉР»РЅРёС‚РµР»РЅРё РёР·РёСЃРєРІР°РЅРёСЏ</label>
                <div className="flex flex-wrap gap-2">
                  {["Р•РєРѕ РјР°С‚РµСЂРёР°Р»Рё", "Р“Р°СЂР°РЅС†РёСЏ 1 Рі.", "РђРІС‚РѕСЂСЃРєРё РЅР°РґР·РѕСЂ", "РџРѕС‡РёСЃС‚РІР°РЅРµ СЃР»РµРґ", "РЎРЅРёРјРєРё РїСЂРµРґРё/СЃР»РµРґ"].map(tag => (
                    <button key={tag} onClick={() => setForm(f => ({
                      ...f, extras: f.extras.includes(tag) ? f.extras.filter(x => x !== tag) : [...f.extras, tag]
                    }))} className={`px-3 py-1.5 rounded-xl text-xs border transition-all
                      ${form.extras.includes(tag) ? "bg-blue-50 border-blue-300 text-blue-700" : "bg-white border-gray-200 text-gray-600 hover:border-blue-200"}`}>
                      {tag}
                    </button>
                  ))}
                </div>
              </div>
            </div>
          </div>
        )}

        {/* в”Ђв”Ђ Step 2: Р‘СЋРґР¶РµС‚ в”Ђв”Ђ */}
        {step === 2 && (
          <div>
            <h2 className="text-gray-800 mb-1">Р‘СЋРґР¶РµС‚ Рё СЃСЂРѕРє</h2>
            <p className="text-sm text-gray-400 mb-6">РџРѕРјР°РіР° РЅРё РґР° РЅР°РјРµСЂРёРј РїРѕРґС…РѕРґСЏС‰РёС‚Рµ РјР°Р№СЃС‚РѕСЂРё Р·Р° РІР°СЃ</p>
            <div className="mb-6">
              <label className="block text-sm text-gray-700 mb-3">РџСЂРёР±Р»РёР·РёС‚РµР»РµРЅ Р±СЋРґР¶РµС‚</label>
              <div className="space-y-2">
                {BUDGETS.map(b => (
                  <button key={b.id} onClick={() => setForm(f => ({ ...f, budget: b.id }))}
                    className={`w-full flex items-center gap-3 px-4 py-3.5 rounded-xl border-2 text-left transition-all
                      ${form.budget === b.id ? "border-blue-500 bg-blue-50" : "border-gray-100 bg-white hover:border-blue-200"}`}>
                    <div className={`size-5 rounded-full border-2 flex items-center justify-center flex-shrink-0
                      ${form.budget === b.id ? "border-blue-500" : "border-gray-300"}`}>
                      {form.budget === b.id && <div className="size-2.5 rounded-full bg-blue-500" />}
                    </div>
                    <div className="flex items-center gap-2 flex-1">
                      <Banknote className={`size-4 ${form.budget === b.id ? "text-blue-500" : "text-gray-400"}`} />
                      <span className={`text-sm ${form.budget === b.id ? "text-blue-700" : "text-gray-700"}`}>{b.label}</span>
                    </div>
                  </button>
                ))}
              </div>
            </div>
            <div>
              <label className="block text-sm text-gray-700 mb-3">РљРѕРіР° РёСЃРєР°С‚Рµ РґР° Р·Р°РїРѕС‡РЅРµ?</label>
              <div className="grid grid-cols-2 gap-3">
                {TIMELINES.map(t => (
                  <button key={t.id} onClick={() => setForm(f => ({ ...f, timeline: t.id }))}
                    className={`p-4 rounded-xl border-2 text-left transition-all
                      ${form.timeline === t.id ? "border-blue-500 bg-blue-50" : "border-gray-100 bg-white hover:border-blue-200"}`}>
                    <div className="flex items-center gap-2 mb-0.5">
                      <Calendar className={`size-3.5 ${form.timeline === t.id ? "text-blue-500" : "text-gray-400"}`} />
                      <p className={`text-sm ${form.timeline === t.id ? "text-blue-700" : "text-gray-800"}`}>{t.label}</p>
                    </div>
                    <p className="text-xs text-gray-400">{t.desc}</p>
                  </button>
                ))}
              </div>
            </div>
          </div>
        )}

        {/* в”Ђв”Ђ Step 3: Р›РѕРєР°С†РёСЏ в”Ђв”Ђ */}
        {step === 3 && (
          <div>
            <h2 className="text-gray-800 mb-1">Р›РѕРєР°С†РёСЏ РЅР° РїСЂРѕРµРєС‚Р°</h2>
            <p className="text-sm text-gray-400 mb-6">Р©Рµ РЅР°РјРµСЂРёРј РјР°Р№СЃС‚РѕСЂРё РІ Р±Р»РёР·РѕСЃС‚ РґРѕ РІР°СЃ</p>
            <div className="space-y-4">
              <div>
                <label className="block text-sm text-gray-700 mb-2">Р“СЂР°Рґ *</label>
                <div className="relative">
                  <MapPin className="absolute left-3.5 top-1/2 -translate-y-1/2 size-4 text-gray-400" />
                  <input type="text" placeholder="РќР°РїСЂ. РЎРѕС„РёСЏ" value={form.city} onChange={e => setForm(f => ({ ...f, city: e.target.value }))}
                    className="w-full pl-10 pr-4 py-3 bg-white border border-gray-200 rounded-xl text-sm text-gray-800 placeholder-gray-400 focus:outline-none focus:ring-2 focus:ring-blue-500/20 focus:border-blue-400 transition-all" />
                </div>
                <div className="flex flex-wrap gap-2 mt-2">
                  {["РЎРѕС„РёСЏ", "РџР»РѕРІРґРёРІ", "Р’Р°СЂРЅР°", "Р‘СѓСЂРіР°СЃ", "Р СѓСЃРµ"].map(c => (
                    <button key={c} onClick={() => setForm(f => ({ ...f, city: c }))}
                      className={`px-3 py-1.5 rounded-lg text-xs border transition-all
                        ${form.city === c ? "bg-blue-50 border-blue-300 text-blue-700" : "bg-white border-gray-200 text-gray-600 hover:border-blue-200"}`}>
                      {c}
                    </button>
                  ))}
                </div>
              </div>
              <div>
                <label className="block text-sm text-gray-700 mb-2">РђРґСЂРµСЃ вЂ” РїРѕ Р¶РµР»Р°РЅРёРµ</label>
                <input type="text" placeholder="РќР°РїСЂ. СѓР». Р’РёС‚РѕС€Р° 12, РµС‚. 3" value={form.address} onChange={e => setForm(f => ({ ...f, address: e.target.value }))}
                  className="w-full px-4 py-3 bg-white border border-gray-200 rounded-xl text-sm text-gray-800 placeholder-gray-400 focus:outline-none focus:ring-2 focus:ring-blue-500/20 focus:border-blue-400 transition-all" />
              </div>
              {/* AI summary */}
              <div className="rounded-2xl bg-gradient-to-r from-blue-50 to-teal-50 border border-blue-100 p-4">
                <div className="flex items-center gap-2 mb-2">
                  <Sparkles className="size-4 text-blue-500" />
                  <span className="text-xs text-blue-700">ZENITH AI РїСЂРµРіР»РµРґ</span>
                </div>
                <p className="text-xs text-gray-600 leading-relaxed">
                  {selectedType?.label && form.description ? (
                    <>РџСЂРѕРµРєС‚ вЂћ<strong>{selectedType.label}</strong>" вЂ” {form.description.slice(0, 60)}вЂ¦
                    {form.budget && <> вЂў Р‘СЋРґР¶РµС‚: {BUDGETS.find(b => b.id === form.budget)?.label}</>}
                    {form.timeline && <> вЂў {TIMELINES.find(t => t.id === form.timeline)?.label}</>}</>
                  ) : "РџРѕРїСЉР»РЅРµС‚Рµ РґРµС‚Р°Р№Р»РёС‚Рµ РїРѕ-РіРѕСЂРµ Р·Р° AI Р°РЅР°Р»РёР·"}
                </p>
              </div>
            </div>
          </div>
        )}

        {/* в”Ђв”Ђ Step 4: Р“РѕС‚РѕРІРѕ / AI РіРµРЅРµСЂРёСЂР° в”Ђв”Ђ */}
        {step === 4 && (
          <div className="text-center py-8">
            {loading ? (
              <div>
                <div className="size-20 rounded-full bg-gradient-to-br from-blue-500 to-teal-500 flex items-center justify-center mx-auto mb-6 shadow-xl shadow-blue-200 animate-pulse">
                  <Sparkles className="size-9 text-white" />
                </div>
                <h2 className="text-gray-800 mb-2">ZENITH AI РѕР±СЂР°Р±РѕС‚РІР°вЂ¦</h2>
                <p className="text-sm text-gray-400">РђРЅР°Р»РёР·РёСЂР°РјРµ РІР°С€РёСЏ РїСЂРѕРµРєС‚ Рё С‚СЉСЂСЃРёРј РїРѕРґС…РѕРґСЏС‰Рё РёР·РїСЉР»РЅРёС‚РµР»Рё</p>
                <div className="flex justify-center gap-1.5 mt-6">
                  {[0, 1, 2].map(i => (
                    <div key={i} className="size-2 rounded-full bg-blue-500 animate-bounce" style={{ animationDelay: `${i * 0.15}s` }} />
                  ))}
                </div>
              </div>
            ) : (
              <div>
                <div className="size-20 rounded-full bg-gradient-to-br from-teal-400 to-blue-500 flex items-center justify-center mx-auto mb-6 shadow-xl shadow-teal-200">
                  <Check className="size-9 text-white" />
                </div>
                <h2 className="text-gray-800 mb-2">РџСЂРѕРµРєС‚СЉС‚ Рµ РїСѓР±Р»РёРєСѓРІР°РЅ! рџЋ‰</h2>
                <p className="text-sm text-gray-500 mb-6">РќР°РјРµСЂРёС…РјРµ <strong className="text-blue-700">8 РёР·РїСЉР»РЅРёС‚РµР»Рё</strong> РІ СЂР°Р№РѕРЅР°. РћС‡Р°РєРІР°Р№С‚Рµ РѕС„РµСЂС‚Рё РІ СЂР°РјРєРёС‚Рµ РЅР° 24 С‡Р°СЃР°.</p>
                <div className="bg-white rounded-2xl border border-gray-100 p-4 text-left mb-6 shadow-sm">
                  <p className="text-xs text-gray-500 mb-2">Р Р•Р—Р®РњР• РќРђ РџР РћР•РљРўРђ</p>
                  {[
                    ["РўРёРї", selectedType?.label],
                    ["Р‘СЋРґР¶РµС‚", BUDGETS.find(b => b.id === form.budget)?.label],
                    ["РЎСЂРѕРє", TIMELINES.find(t => t.id === form.timeline)?.label],
                    ["Р“СЂР°Рґ", form.city],
                  ].map(([k, v]) => v && (
                    <div key={k} className="flex justify-between py-2 border-b border-gray-50 last:border-0">
                      <span className="text-xs text-gray-400">{k}</span>
                      <span className="text-xs text-gray-800">{v}</span>
                    </div>
                  ))}
                </div>
                <div className="flex gap-3 justify-center flex-wrap">
                  <button onClick={() => navigate("/client/projects")} className="flex items-center gap-2 px-5 py-2.5 rounded-xl bg-blue-600 text-white text-sm hover:bg-blue-700 transition-colors shadow-md shadow-blue-200">
                    <FileText className="size-4" />
                    РњРѕРёС‚Рµ РїСЂРѕРµРєС‚Рё
                  </button>
                  <button onClick={() => { setStep(0); setForm({ type: "", description: "", area: "", budget: "", timeline: "", city: "", address: "", extras: [] }); setDone(false); }}
                    className="flex items-center gap-2 px-5 py-2.5 rounded-xl bg-gray-100 text-gray-700 text-sm hover:bg-gray-200 transition-colors">
                    <Send className="size-4" />
                    РќРѕРІ РїСЂРѕРµРєС‚
                  </button>
                </div>
              </div>
            )}
          </div>
        )}

        {/* Nav buttons */}
        {step < 4 && (
          <div className="flex gap-3 mt-8">
            {step > 0 && (
              <button onClick={() => setStep(s => s - 1)}
                className="flex items-center gap-2 px-5 py-3 rounded-xl bg-gray-100 text-gray-700 text-sm hover:bg-gray-200 transition-colors">
                <ChevronLeft className="size-4" />РќР°Р·Р°Рґ
              </button>
            )}
            <button onClick={handleNext} disabled={!canNext()}
              className={`flex-1 flex items-center justify-center gap-2 px-5 py-3 rounded-xl text-white text-sm transition-all
                ${canNext() ? "bg-blue-600 hover:bg-blue-700 shadow-md shadow-blue-200" : "bg-gray-200 text-gray-400 cursor-not-allowed"}`}>
              {step === 3 ? (
                <><Sparkles className="size-4" />РџСѓР±Р»РёРєСѓРІР°Р№ СЃ AI</>
              ) : (
                <>РќР°РїСЂРµРґ<ChevronRight className="size-4" /></>
              )}
            </button>
          </div>
        )}
      </div>
    </div>
  );
}



// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ
// FILE: src/app/pages/client/ProjectsPage.tsx
// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ

import { useState } from "react";
import { useNavigate } from "react-router";
import {
  Plus, Search, Filter, Clock, CheckCircle2,
  AlertCircle, TrendingUp, MessageSquare, Eye, MoreHorizontal, Calendar,
} from "lucide-react";

const PROJECTS = [
  {
    id: 1, name: "Р РµРјРѕРЅС‚ Р±Р°РЅСЏ вЂ” СѓР». Р’РёС‚РѕС€Р° 12", type: "Р‘Р°РЅСЏ",
    status: "active", progress: 65, budget: "4 200 Р»РІ",
    img: "https://images.unsplash.com/photo-1612153284972-7e80a48abcb9?w=600&q=80",
    contractor: "Р“РµРѕСЂРіРё РЎС‚СЂРѕРµРІ", contractorImg: "https://images.unsplash.com/photo-1728516687003-58347d3412b3?w=100&q=80",
    eta: "12 Р°РїСЂ 2026", messages: 3, startDate: "20 РјР°СЂ 2026",
  },
  {
    id: 2, name: "Р‘РѕСЏРґРёСЃРІР°РЅРµ С…РѕР» + РєСѓС…РЅСЏ", type: "Р‘РѕСЏРґРёСЃРІР°РЅРµ",
    status: "pending", progress: 5, budget: "1 800 Р»РІ",
    img: "https://images.unsplash.com/photo-1760072513442-9872656c1b07?w=600&q=80",
    contractor: "Р§Р°РєР° РѕС„РµСЂС‚Рё", contractorImg: "",
    eta: "вЂ”", messages: 0, startDate: "1 Р°РїСЂ 2026",
  },
  {
    id: 3, name: "РџРѕРґРјСЏРЅР° Р’РёРљ вЂ” РєСѓС…РЅСЏ", type: "Р’РёРљ",
    status: "done", progress: 100, budget: "950 Р»РІ",
    img: "https://images.unsplash.com/photo-1771862956702-4e8b247e28b5?w=600&q=80",
    contractor: "РњР°СЂС‚РёРЅ Р”РёРјРёС‚СЂРѕРІ", contractorImg: "https://images.unsplash.com/photo-1621905252472-943afaa20e20?w=100&q=80",
    eta: "Р—Р°РІСЉСЂС€РµРЅ", messages: 0, startDate: "10 РјР°СЂ 2026",
  },
  {
    id: 4, name: "РЎРјСЏРЅР° РґРѕРіСЂР°РјР° вЂ” 4 РїСЂРѕР·РѕСЂРµС†Р°", type: "Р”РѕРіСЂР°РјР°",
    status: "done", progress: 100, budget: "2 400 Р»РІ",
    img: "https://images.unsplash.com/photo-1636200534256-c08268363482?w=600&q=80",
    contractor: "РЎС‚СЂРѕР№ РџР»СЋСЃ РћРћР”", contractorImg: "",
    eta: "Р—Р°РІСЉСЂС€РµРЅ", messages: 1, startDate: "5 С„РµРІ 2026",
  },
  {
    id: 5, name: "Р›Р°РјРёРЅРёСЂР°РЅ РїР°СЂРєРµС‚ вЂ” СЃРїР°Р»РЅСЏ 14 РєРІ.Рј", type: "РџРѕРґРѕРІРё",
    status: "active", progress: 40, budget: "1 600 Р»РІ",
    img: "https://images.unsplash.com/photo-1649719742478-830ba2e55b5d?w=600&q=80",
    contractor: "РРІР°РЅ РџР°СЂРєРµС‚РѕРІ", contractorImg: "",
    eta: "20 Р°РїСЂ 2026", messages: 2, startDate: "28 РјР°СЂ 2026",
  },
];

const TABS = [
  { key: "all",     label: "Р’СЃРёС‡РєРё",   icon: Filter },
  { key: "active",  label: "РђРєС‚РёРІРЅРё",  icon: TrendingUp },
  { key: "pending", label: "Р§Р°РєР°С‰Рё",   icon: AlertCircle },
  { key: "done",    label: "Р—Р°РІСЉСЂС€РµРЅРё",icon: CheckCircle2 },
];

const STATUS_STYLE: Record<string, { label: string; cls: string; dot: string; icon: typeof Clock }> = {
  active:  { label: "Р’ С…РѕРґ",       cls: "bg-blue-50 text-blue-700 border-blue-100",    dot: "bg-blue-500",  icon: TrendingUp },
  pending: { label: "Р§Р°РєР° РѕС„РµСЂС‚Р°", cls: "bg-amber-50 text-amber-700 border-amber-100", dot: "bg-amber-400", icon: Clock },
  done:    { label: "Р—Р°РІСЉСЂС€РµРЅ",    cls: "bg-green-50 text-green-700 border-green-100",  dot: "bg-green-500", icon: CheckCircle2 },
};

export function ProjectsPage() {
  const navigate = useNavigate();
  const [tab, setTab] = useState("all");
  const [search, setSearch] = useState("");

  const filtered = PROJECTS.filter(p =>
    (tab === "all" || p.status === tab) &&
    (p.name.toLowerCase().includes(search.toLowerCase()) || p.type.toLowerCase().includes(search.toLowerCase()))
  );

  const counts = {
    all: PROJECTS.length,
    active: PROJECTS.filter(p => p.status === "active").length,
    pending: PROJECTS.filter(p => p.status === "pending").length,
    done: PROJECTS.filter(p => p.status === "done").length,
  };

  return (
    <div className="p-5 lg:p-8">
      {/* Header */}
      <div className="flex items-center justify-between mb-6">
        <div>
          <h1 className="text-gray-800">РњРѕРёС‚Рµ РїСЂРѕРµРєС‚Рё</h1>
          <p className="text-sm text-gray-400">{PROJECTS.length} РїСЂРѕРµРєС‚Р° РѕР±С‰Рѕ</p>
        </div>
        <button onClick={() => navigate("/client/project-wizard")}
          className="flex items-center gap-2 px-4 py-2.5 rounded-xl bg-blue-600 text-white text-sm hover:bg-blue-700 transition-all shadow-md shadow-blue-200 active:scale-95">
          <Plus className="size-4" />
          <span className="hidden sm:inline">РќРѕРІ РїСЂРѕРµРєС‚</span>
        </button>
      </div>

      {/* Stats row */}
      <div className="grid grid-cols-3 gap-3 mb-6">
        {[
          { label: "РђРєС‚РёРІРЅРё",   v: counts.active,  color: "text-blue-600",  bg: "bg-blue-50",  icon: TrendingUp },
          { label: "Р§Р°РєР°С‰Рё",    v: counts.pending, color: "text-amber-600", bg: "bg-amber-50", icon: Clock },
          { label: "Р—Р°РІСЉСЂС€РµРЅРё", v: counts.done,    color: "text-green-600", bg: "bg-green-50", icon: CheckCircle2 },
        ].map(s => (
          <div key={s.label} className="bg-white rounded-2xl border border-gray-100 px-4 py-3 flex items-center gap-3 shadow-sm">
            <div className={`size-8 rounded-xl ${s.bg} flex items-center justify-center flex-shrink-0`}>
              <s.icon className={`size-4 ${s.color}`} />
            </div>
            <div>
              <p className={`text-lg font-semibold ${s.color}`}>{s.v}</p>
              <p className="text-xs text-gray-400">{s.label}</p>
            </div>
          </div>
        ))}
      </div>

      {/* Search + Tabs */}
      <div className="flex flex-col sm:flex-row gap-3 mb-5">
        <div className="relative flex-1">
          <Search className="absolute left-3.5 top-1/2 -translate-y-1/2 size-4 text-gray-400 pointer-events-none" />
          <input placeholder="РўСЉСЂСЃРё РїРѕ РїСЂРѕРµРєС‚ РёР»Рё С‚РёРївЂ¦" value={search} onChange={e => setSearch(e.target.value)}
            className="w-full pl-10 pr-4 py-2.5 bg-white border border-gray-200 rounded-xl text-sm text-gray-800 placeholder-gray-400 focus:outline-none focus:ring-2 focus:ring-blue-500/20 focus:border-blue-400 transition-all" />
        </div>
        <div className="flex gap-1.5 bg-gray-100 p-1 rounded-xl">
          {TABS.map(t => (
            <button key={t.key} onClick={() => setTab(t.key)}
              className={`flex items-center gap-1.5 px-3 py-1.5 rounded-lg text-xs transition-all
                ${tab === t.key ? "bg-white text-blue-700 shadow-sm" : "text-gray-500 hover:text-gray-700"}`}>
              {t.label}
              <span className={`size-4 rounded-full flex items-center justify-center text-xs
                ${tab === t.key ? "bg-blue-100 text-blue-700" : "bg-gray-200 text-gray-500"}`}>
                {counts[t.key as keyof typeof counts]}
              </span>
            </button>
          ))}
        </div>
      </div>

      {/* Projects grid */}
      {filtered.length === 0 ? (
        <div className="bg-white rounded-2xl border border-gray-100 p-12 text-center">
          <div className="size-14 bg-gray-50 rounded-2xl flex items-center justify-center mx-auto mb-3">
            <Search className="size-6 text-gray-300" />
          </div>
          <p className="text-sm text-gray-500">РќСЏРјР° РЅР°РјРµСЂРµРЅРё РїСЂРѕРµРєС‚Рё</p>
        </div>
      ) : (
        <div className="grid grid-cols-1 sm:grid-cols-2 xl:grid-cols-3 gap-4">
          {filtered.map(p => {
            const s = STATUS_STYLE[p.status];
            return (
              <div key={p.id} className="group bg-white rounded-2xl border border-gray-100 overflow-hidden shadow-sm hover:shadow-lg transition-all duration-300">
                {/* Image */}
                <div className="relative h-40 overflow-hidden">
                  <img src={p.img} alt={p.name} className="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500" />
                  <div className="absolute inset-0 bg-gradient-to-t from-black/60 to-transparent" />
                  <div className="absolute top-3 left-3">
                    <span className={`flex items-center gap-1.5 px-2.5 py-1 rounded-full text-xs border backdrop-blur-sm bg-white/90 ${s.cls}`}>
                      <span className={`size-1.5 rounded-full ${s.dot}`} />
                      {s.label}
                    </span>
                  </div>
                  <div className="absolute top-3 right-3">
                    <span className="px-2.5 py-1 rounded-full bg-black/40 backdrop-blur-sm text-white text-xs">{p.budget}</span>
                  </div>
                  <div className="absolute bottom-3 left-3">
                    <span className="px-2 py-0.5 rounded-lg bg-white/20 backdrop-blur-sm text-white text-xs">{p.type}</span>
                  </div>
                </div>

                {/* Content */}
                <div className="p-4">
                  <h3 className="text-sm text-gray-800 mb-3 leading-snug">{p.name}</h3>

                  {/* Progress */}
                  <div className="mb-3">
                    <div className="flex justify-between mb-1.5">
                      <span className="text-xs text-gray-400">РќР°РїСЂРµРґСЉРє</span>
                      <span className={`text-xs font-medium ${p.status === "done" ? "text-green-600" : "text-blue-600"}`}>{p.progress}%</span>
                    </div>
                    <div className="h-1.5 bg-gray-100 rounded-full overflow-hidden">
                      <div className={`h-full rounded-full transition-all ${p.status === "done" ? "bg-gradient-to-r from-teal-400 to-green-500" : "bg-gradient-to-r from-blue-500 to-teal-500"}`}
                        style={{ width: `${p.progress}%` }} />
                    </div>
                  </div>

                  <div className="flex items-center justify-between">
                    <div className="flex items-center gap-1.5">
                      {p.contractorImg ? (
                        <img src={p.contractorImg} alt="" className="size-6 rounded-full object-cover" />
                      ) : (
                        <div className="size-6 rounded-full bg-gradient-to-br from-blue-400 to-teal-400 flex items-center justify-center text-white text-xs flex-shrink-0">
                          {p.contractor[0]}
                        </div>
                      )}
                      <span className="text-xs text-gray-600">{p.contractor}</span>
                    </div>
                    <div className="flex items-center gap-2">
                      {p.messages > 0 && (
                        <span className="flex items-center gap-1 text-xs text-blue-600 bg-blue-50 px-2 py-0.5 rounded-lg">
                          <MessageSquare className="size-3" />{p.messages}
                        </span>
                      )}
                      <button className="size-7 flex items-center justify-center rounded-lg hover:bg-gray-100 text-gray-400 transition-colors">
                        <MoreHorizontal className="size-4" />
                      </button>
                    </div>
                  </div>

                  <div className="flex items-center gap-1.5 mt-3 pt-3 border-t border-gray-50">
                    <Calendar className="size-3 text-gray-400" />
                    <span className="text-xs text-gray-400">
                      {p.status === "done" ? "Р—Р°РІСЉСЂС€РµРЅ" : `РљСЂР°РµРЅ СЃСЂРѕРє: ${p.eta}`}
                    </span>
                  </div>
                </div>

                {/* Actions */}
                <div className="px-4 pb-4 flex gap-2">
                  <button className="flex-1 flex items-center justify-center gap-1.5 py-2 rounded-xl bg-blue-50 text-blue-700 text-xs hover:bg-blue-100 transition-colors">
                    <Eye className="size-3.5" />Р”РµС‚Р°Р№Р»Рё
                  </button>
                  {p.status !== "done" && (
                    <button onClick={() => navigate("/client/chat")}
                      className="flex-1 flex items-center justify-center gap-1.5 py-2 rounded-xl bg-gray-50 text-gray-700 text-xs hover:bg-gray-100 transition-colors">
                      <MessageSquare className="size-3.5" />Р§Р°С‚
                    </button>
                  )}
                </div>
              </div>
            );
          })}

          {/* Add new */}
          <button onClick={() => navigate("/client/project-wizard")}
            className="group border-2 border-dashed border-gray-200 rounded-2xl flex flex-col items-center justify-center gap-3 min-h-[280px] hover:border-blue-300 hover:bg-blue-50/50 transition-all">
            <div className="size-12 rounded-2xl bg-blue-50 group-hover:bg-blue-100 flex items-center justify-center transition-colors">
              <Plus className="size-6 text-blue-500" />
            </div>
            <p className="text-sm text-gray-600 group-hover:text-blue-700 transition-colors">РќРѕРІ РїСЂРѕРµРєС‚</p>
          </button>
        </div>
      )}
    </div>
  );
}



// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ
// FILE: src/app/pages/client/ChatPage.tsx
// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ

import { useState, useRef, useEffect } from "react";
import {
  Search, Send, Phone, Video, MoreVertical,
  Check, CheckCheck, Paperclip, Smile, Image, ChevronLeft,
} from "lucide-react";

const CONVERSATIONS = [
  {
    id: 1, name: "Р“РµРѕСЂРіРё РЎС‚СЂРѕРµРІ", role: "Р’РёРљ СЃРїРµС†РёР°Р»РёСЃС‚", online: true,
    img: "https://images.unsplash.com/photo-1728516687003-58347d3412b3?w=100&q=80",
    lastMsg: "Р©Рµ РґРѕР№РґР° СѓС‚СЂРµ РІ 10:00 Р·Р° С„РёРЅР°Р»РЅРёСЏ РѕРіР»РµРґ", time: "10:42", unread: 2, project: "Р РµРјРѕРЅС‚ Р±Р°РЅСЏ",
  },
  {
    id: 2, name: "РњР°СЂС‚РёРЅ Р”РёРјРёС‚СЂРѕРІ", role: "РЎС‚СЂРѕРёС‚РµР»РµРЅ РјР°Р№СЃС‚РѕСЂ", online: false,
    img: "https://images.unsplash.com/photo-1621905252472-943afaa20e20?w=100&q=80",
    lastMsg: "РР·РїСЂР°С‚РёС… С„Р°РєС‚СѓСЂР°С‚Р° РїРѕ РёРјРµР№Р»", time: "Р’С‡РµСЂР°", unread: 0, project: "Р’РёРљ РєСѓС…РЅСЏ",
  },
  {
    id: 3, name: "РЎС‚СЂРѕР№ РџР»СЋСЃ РћРћР”", role: "РЎС‚СЂРѕРёС‚РµР»РЅР° С„РёСЂРјР°", online: true,
    img: "",
    lastMsg: "РћС„РµСЂС‚Р°С‚Р° Рµ РіРѕС‚РѕРІР°, РІРёР¶ СЏ РІ РґРѕРєСѓРјРµРЅС‚РёС‚Рµ", time: "Р’С‡РµСЂР°", unread: 1, project: "Р”РѕРіСЂР°РјР°",
  },
  {
    id: 4, name: "IРІР°РЅ РџР°СЂРєРµС‚РѕРІ", role: "РџР°СЂРєРµС‚РёСЃС‚", online: false,
    img: "",
    lastMsg: "Р”РѕР±СЂРµ, С‰Рµ РІР·РµРјР° РјРѕСЃС‚СЂРёС‚Рµ РѕС‚ СЃРєР»Р°РґР°", time: "2 Р°РїСЂ", unread: 0, project: "РџР°СЂРєРµС‚ СЃРїР°Р»РЅСЏ",
  },
];

const MESSAGES: Record<number, Array<{ id: number; text: string; mine: boolean; time: string; read: boolean }>> = {
  1: [
    { id: 1, text: "Р—РґСЂР°РІРµР№С‚Рµ, РёСЃРєР°С… РґР° РїРѕРїРёС‚Р°Рј Р·Р° РїР»РѕС‡РєРёС‚Рµ РІ Р±Р°РЅСЏС‚Р° вЂ” РёРјР°С‚Рµ Р»Рё РїСЂРµРґРїРѕС‡РёС‚Р°РЅРёСЏ Р·Р° РјРѕРґРµР»?", mine: true, time: "09:15", read: true },
    { id: 2, text: "Р”Р°, РёРјР°Рј 3 РІР°СЂРёР°РЅС‚Р° Р·Р° РїРѕРєР°Р·РІР°РЅРµ. Р©Рµ РІРё РіРё РёР·РїСЂР°С‚СЏ РєР°С‚Рѕ СЃРЅРёРјРєРё.", mine: false, time: "09:18", read: true },
    { id: 3, text: "РћС‚Р»РёС‡РЅРѕ! Р©Рµ С‡Р°РєР°Рј", mine: true, time: "09:19", read: true },
    { id: 4, text: "Р•С‚Рѕ РіРё вЂ” РІР°СЂРёР°РЅС‚Рё Рђ, Р‘ Рё Р’. Р’Р°СЂРёРЅС‚ Р‘ Рµ 20% РїРѕ-СЃРєСЉРї, РЅРѕ Рµ РїРѕ-РєР°С‡РµСЃС‚РІРµРЅ.", mine: false, time: "09:35", read: true },
    { id: 5, text: "РҐР°СЂРµСЃР° РјРё РІР°СЂРёР°РЅС‚ Р‘. РљРѕР»РєРѕ С‰Рµ СЃРµ РѕС‚СЂР°Р·Рё РЅР° Р±СЋРґР¶РµС‚Р°?", mine: true, time: "09:52", read: true },
    { id: 6, text: "РћРєРѕР»Рѕ 350 Р»РІ РїРѕРІРµС‡Рµ. РњРѕРіР° РґР° РєРѕРјРїРµРЅСЃРёСЂР°Рј РѕС‚ РјР°С‚РµСЂРёР°Р»РёС‚Рµ Р·Р° СЃРёР»РёРєРѕРЅР°.", mine: false, time: "10:01", read: true },
    { id: 7, text: "РџРµСЂС„РµРєС‚РЅРѕ! Р”Р° РІР·РµРјРµРј РІР°СЂРёР°РЅС‚ Р‘ С‚РѕРіР°РІР°.", mine: true, time: "10:15", read: true },
    { id: 8, text: "Р©Рµ РґРѕР№РґР° СѓС‚СЂРµ РІ 10:00 Р·Р° С„РёРЅР°Р»РЅРёСЏ РѕРіР»РµРґ", mine: false, time: "10:42", read: false },
  ],
  2: [
    { id: 1, text: "РџСЂРѕРµРєС‚СЉС‚ Рµ Р·Р°РІСЉСЂС€РµРЅ. РР·РїСЂР°С‚РёС… С„Р°РєС‚СѓСЂР°С‚Р° РїРѕ РёРјРµР№Р».", mine: false, time: "Р’С‡РµСЂР° 14:22", read: true },
    { id: 2, text: "РџРѕР»СѓС‡РёС… СЏ, Р±Р»Р°РіРѕРґР°СЂСЏ! Р Р°Р±РѕС‚Р°С‚Р° Р±РµС€Рµ РїРµСЂС„РµРєС‚РЅР°.", mine: true, time: "Р’С‡РµСЂР° 15:10", read: true },
    { id: 3, text: "РР·РїСЂР°С‚РёС… С„Р°РєС‚СѓСЂР°С‚Р° РїРѕ РёРјРµР№Р»", mine: false, time: "Р’С‡РµСЂР° 15:12", read: true },
  ],
  3: [
    { id: 1, text: "РћС„РµСЂС‚Р°С‚Р° Р·Р° СЃРјСЏРЅР° РЅР° 4 РїСЂРѕР·РѕСЂРµС†Р° Рµ РіРѕС‚РѕРІР°.", mine: false, time: "Р’С‡РµСЂР° 11:00", read: false },
  ],
  4: [
    { id: 1, text: "РњРѕСЃС‚СЂРёС‚Рµ Р·Р° РїР°СЂРєРµС‚Р° С‰Рµ РіРё РІР·РµРјР° РѕС‚ СЃРєР»Р°РґР° СѓС‚СЂРµ.", mine: false, time: "2 Р°РїСЂ 16:45", read: true },
    { id: 2, text: "Р”РѕР±СЂРµ, С‰Рµ РІР·РµРјР° РјРѕСЃС‚СЂРёС‚Рµ РѕС‚ СЃРєР»Р°РґР°", mine: false, time: "2 Р°РїСЂ 17:00", read: true },
  ],
};

export function ChatPage() {
  const [activeId, setActiveId] = useState<number | null>(1);
  const [search, setSearch] = useState("");
  const [input, setInput] = useState("");
  const [messages, setMessages] = useState(MESSAGES);
  const [showList, setShowList] = useState(true);
  const bottomRef = useRef<HTMLDivElement>(null);

  const active = CONVERSATIONS.find(c => c.id === activeId);
  const activeMsgs = activeId ? (messages[activeId] || []) : [];

  useEffect(() => {
    bottomRef.current?.scrollIntoView({ behavior: "smooth" });
  }, [activeMsgs]);

  const sendMsg = () => {
    if (!input.trim() || !activeId) return;
    const newMsg = { id: Date.now(), text: input.trim(), mine: true, time: "СЃРµРіР°", read: false };
    setMessages(m => ({ ...m, [activeId]: [...(m[activeId] || []), newMsg] }));
    setInput("");
  };

  const filtered = CONVERSATIONS.filter(c =>
    c.name.toLowerCase().includes(search.toLowerCase()) || c.project.toLowerCase().includes(search.toLowerCase())
  );

  return (
    <div className="flex h-[calc(100vh-4rem)] overflow-hidden">
      {/* в”Ђв”Ђ Sidebar list в”Ђв”Ђ */}
      <div className={`${showList ? "flex" : "hidden"} md:flex flex-col w-full md:w-72 lg:w-80 bg-white border-r border-gray-100 flex-shrink-0`}>
        <div className="p-4 border-b border-gray-100">
          <h1 className="text-gray-800 mb-3">Р§Р°С‚РѕРІРµ</h1>
          <div className="relative">
            <Search className="absolute left-3 top-1/2 -translate-y-1/2 size-3.5 text-gray-400 pointer-events-none" />
            <input placeholder="РўСЉСЂСЃРё СЂР°Р·РіРѕРІРѕСЂвЂ¦" value={search} onChange={e => setSearch(e.target.value)}
              className="w-full pl-9 pr-3 py-2 bg-gray-50 border border-gray-200 rounded-xl text-xs text-gray-700 placeholder-gray-400 focus:outline-none focus:ring-2 focus:ring-blue-500/20 focus:border-blue-400 transition-all" />
          </div>
        </div>
        <div className="flex-1 overflow-y-auto">
          {filtered.map(c => (
            <button key={c.id} onClick={() => { setActiveId(c.id); setShowList(false); }}
              className={`w-full flex items-start gap-3 px-4 py-3.5 text-left transition-colors border-b border-gray-50
                ${activeId === c.id ? "bg-blue-50" : "hover:bg-gray-50"}`}>
              <div className="relative flex-shrink-0">
                {c.img ? (
                  <img src={c.img} alt={c.name} className="size-10 rounded-full object-cover" />
                ) : (
                  <div className="size-10 rounded-full bg-gradient-to-br from-blue-400 to-teal-400 flex items-center justify-center text-white text-sm">
                    {c.name[0]}
                  </div>
                )}
                {c.online && <span className="absolute bottom-0 right-0 size-2.5 rounded-full bg-green-400 border-2 border-white" />}
              </div>
              <div className="flex-1 min-w-0">
                <div className="flex items-center justify-between mb-0.5">
                  <p className={`text-sm truncate ${activeId === c.id ? "text-blue-700" : "text-gray-800"}`}>{c.name}</p>
                  <span className="text-xs text-gray-400 flex-shrink-0 ml-2">{c.time}</span>
                </div>
                <p className="text-xs text-gray-400 truncate">{c.lastMsg}</p>
                <p className="text-xs text-blue-400 mt-0.5">{c.project}</p>
              </div>
              {c.unread > 0 && (
                <span className="size-5 rounded-full bg-blue-600 text-white text-xs flex items-center justify-center flex-shrink-0 mt-1">
                  {c.unread}
                </span>
              )}
            </button>
          ))}
        </div>
      </div>

      {/* в”Ђв”Ђ Chat window в”Ђв”Ђ */}
      <div className={`${!showList || activeId ? "flex" : "hidden"} md:flex flex-col flex-1 min-w-0`}>
        {active ? (
          <>
            {/* Chat header */}
            <div className="h-16 bg-white border-b border-gray-100 flex items-center gap-3 px-4 flex-shrink-0">
              <button onClick={() => setShowList(true)} className="md:hidden size-8 flex items-center justify-center rounded-lg hover:bg-gray-100 text-gray-500 transition-colors">
                <ChevronLeft className="size-5" />
              </button>
              <div className="relative flex-shrink-0">
                {active.img ? (
                  <img src={active.img} alt={active.name} className="size-9 rounded-full object-cover" />
                ) : (
                  <div className="size-9 rounded-full bg-gradient-to-br from-blue-400 to-teal-400 flex items-center justify-center text-white text-sm">
                    {active.name[0]}
                  </div>
                )}
                {active.online && <span className="absolute bottom-0 right-0 size-2.5 rounded-full bg-green-400 border-2 border-white" />}
              </div>
              <div className="flex-1 min-w-0">
                <p className="text-sm text-gray-800">{active.name}</p>
                <p className="text-xs text-gray-400">{active.online ? "РћРЅР»Р°Р№РЅ" : "РџРѕСЃР»РµРґРЅРѕ РІРёР¶РґР°РЅ РІС‡РµСЂР°"} В· {active.project}</p>
              </div>
              <div className="flex items-center gap-1">
                <button className="size-9 flex items-center justify-center rounded-xl hover:bg-gray-100 text-gray-500 transition-colors"><Phone className="size-4" /></button>
                <button className="size-9 flex items-center justify-center rounded-xl hover:bg-gray-100 text-gray-500 transition-colors"><Video className="size-4" /></button>
                <button className="size-9 flex items-center justify-center rounded-xl hover:bg-gray-100 text-gray-500 transition-colors"><MoreVertical className="size-4" /></button>
              </div>
            </div>

            {/* Messages */}
            <div className="flex-1 overflow-y-auto px-4 py-4 space-y-3 bg-gray-50">
              {activeMsgs.map(m => (
                <div key={m.id} className={`flex ${m.mine ? "justify-end" : "justify-start"}`}>
                  {!m.mine && (
                    <div className="size-7 rounded-full bg-gradient-to-br from-blue-400 to-teal-400 flex items-center justify-center text-white text-xs mr-2 flex-shrink-0 mt-auto">
                      {active.name[0]}
                    </div>
                  )}
                  <div className={`max-w-[75%] rounded-2xl px-4 py-2.5 shadow-sm
                    ${m.mine ? "bg-blue-600 text-white rounded-br-sm" : "bg-white text-gray-800 rounded-bl-sm border border-gray-100"}`}>
                    <p className="text-sm leading-relaxed">{m.text}</p>
                    <div className={`flex items-center gap-1 mt-1 ${m.mine ? "justify-end" : "justify-start"}`}>
                      <span className={`text-xs ${m.mine ? "text-blue-200" : "text-gray-400"}`}>{m.time}</span>
                      {m.mine && (m.read ? <CheckCheck className="size-3 text-blue-200" /> : <Check className="size-3 text-blue-300" />)}
                    </div>
                  </div>
                </div>
              ))}
              <div ref={bottomRef} />
            </div>

            {/* Input */}
            <div className="bg-white border-t border-gray-100 p-4 flex-shrink-0">
              <div className="flex items-end gap-2">
                <div className="flex items-center gap-1 flex-shrink-0">
                  <button className="size-9 flex items-center justify-center rounded-xl hover:bg-gray-100 text-gray-400 transition-colors"><Paperclip className="size-4" /></button>
                  <button className="size-9 flex items-center justify-center rounded-xl hover:bg-gray-100 text-gray-400 transition-colors"><Image className="size-4" /></button>
                </div>
                <div className="flex-1 relative">
                  <textarea rows={1} placeholder="РќР°РїРёС€РµС‚Рµ СЃСЉРѕР±С‰РµРЅРёРµвЂ¦" value={input}
                    onChange={e => setInput(e.target.value)}
                    onKeyDown={e => { if (e.key === "Enter" && !e.shiftKey) { e.preventDefault(); sendMsg(); } }}
                    className="w-full px-4 py-2.5 bg-gray-50 border border-gray-200 rounded-2xl text-sm text-gray-800 placeholder-gray-400 focus:outline-none focus:ring-2 focus:ring-blue-500/20 focus:border-blue-400 resize-none transition-all pr-10"
                    style={{ minHeight: 44, maxHeight: 120 }} />
                  <button className="absolute right-3 bottom-2 text-gray-400 hover:text-gray-600 transition-colors"><Smile className="size-4" /></button>
                </div>
                <button onClick={sendMsg} disabled={!input.trim()}
                  className={`size-10 flex items-center justify-center rounded-xl flex-shrink-0 transition-all
                    ${input.trim() ? "bg-blue-600 text-white hover:bg-blue-700 shadow-md shadow-blue-200" : "bg-gray-100 text-gray-400"}`}>
                  <Send className="size-4" />
                </button>
              </div>
            </div>
          </>
        ) : (
          <div className="flex-1 flex items-center justify-center bg-gray-50">
            <div className="text-center">
              <div className="size-16 rounded-2xl bg-blue-50 flex items-center justify-center mx-auto mb-3">
                <Send className="size-7 text-blue-300" />
              </div>
              <p className="text-sm text-gray-500">РР·Р±РµСЂРµС‚Рµ СЂР°Р·РіРѕРІРѕСЂ РѕС‚ Р»СЏРІРѕС‚Рѕ РјРµРЅСЋ</p>
            </div>
          </div>
        )}
      </div>
    </div>
  );
}



// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ
// FILE: src/app/pages/client/MarketplacePage.tsx
// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ

import { useState } from "react";
import { useNavigate } from "react-router";
import {
  Search, Star, ShieldCheck, MapPin, MessageSquare,
  Filter, ChevronDown, Zap, Clock, CheckCircle2, Heart,
} from "lucide-react";

const PROS = [
  {
    id: 1, name: "Р“РµРѕСЂРіРё РЎС‚СЂРѕРµРІ", specialty: "Р’РёРљ & Р‘Р°РЅСЏ", rating: 4.9, reviews: 89, jobs: 127,
    img: "https://images.unsplash.com/photo-1728516687003-58347d3412b3?w=300&q=80",
    badge: "РўРѕРї РёР·РїСЉР»РЅРёС‚РµР»", city: "РЎРѕС„РёСЏ", price: "45 Р»РІ/С‡", eta: "РЎРІРѕР±РѕРґРµРЅ СЃРµРіР°",
    tags: ["Р’РёРљ", "Р‘Р°РЅСЏ", "РџР»РѕС‡РєРё", "РҐРёРґСЂРѕРёР·РѕР»Р°С†РёСЏ"], verified: true, online: true,
  },
  {
    id: 2, name: "РњР°СЂС‚РёРЅ Р”РёРјРёС‚СЂРѕРІ", specialty: "РћР±С‰Рѕ СЃС‚СЂРѕРёС‚РµР»СЃС‚РІРѕ", rating: 4.8, reviews: 64, jobs: 89,
    img: "https://images.unsplash.com/photo-1621905252472-943afaa20e20?w=300&q=80",
    badge: "РџСЂРѕРІРµСЂРµРЅ", city: "РЎРѕС„РёСЏ", price: "50 Р»РІ/С‡", eta: "РЎРІРѕР±РѕРґРµРЅ РѕС‚ 8 Р°РїСЂ",
    tags: ["Р—РёРґР°СЂРёСЏ", "РњР°Р·РёР»РєР°", "Р‘РµС‚РѕРЅ", "РљРѕРЅСЃС‚СЂСѓРєС†РёСЏ"], verified: true, online: false,
  },
  {
    id: 3, name: "Р•Р»РµРЅР° Р’Р°СЃРёР»РµРІР°", specialty: "РРЅС‚РµСЂРёРѕСЂРµРЅ РґРёР·Р°Р№РЅ", rating: 5.0, reviews: 42, jobs: 56,
    img: "https://images.unsplash.com/photo-1770058428154-9eee8a6a1fbb?w=300&q=80",
    badge: "РўРѕРї РёР·РїСЉР»РЅРёС‚РµР»", city: "РџР»РѕРІРґРёРІ", price: "80 Р»РІ/С‡", eta: "РЎРІРѕР±РѕРґРЅР°",
    tags: ["Р”РёР·Р°Р№РЅ", "3D Р’РёР·СѓР°Р»РёР·Р°С†РёСЏ", "РџСЂРѕРµРєС‚", "РћР±Р·Р°РІРµР¶РґР°РЅРµ"], verified: true, online: true,
  },
  {
    id: 4, name: "РЎС‚СЂРѕР№ РџР»СЋСЃ РћРћР”", specialty: "Р”РѕРіСЂР°РјР° & РџСЂРѕР·РѕСЂС†Рё", rating: 4.7, reviews: 35, jobs: 180,
    img: "https://images.unsplash.com/photo-1659353588580-8da374e328a1?w=300&q=80",
    badge: "Р¤РёСЂРјР°", city: "РЎРѕС„РёСЏ", price: "РџРѕ РѕС„РµСЂС‚Р°", eta: "РЎРІРѕР±РѕРґРЅРё РѕС‚ 10 Р°РїСЂ",
    tags: ["PVC РґРѕРіСЂР°РјР°", "РђР»СѓРјРёРЅРёР№", "РЎС‚СЉРєР»РѕРїР°РєРµС‚", "РњРѕРЅС‚Р°Р¶"], verified: true, online: true,
  },
  {
    id: 5, name: "РРІР°РЅ РџР°СЂРєРµС‚РѕРІ", specialty: "РџР°СЂРєРµС‚ & РџРѕРґРѕРІРё", rating: 4.9, reviews: 51, jobs: 93,
    img: "https://images.unsplash.com/photo-1627660080110-20045fd3875d?w=300&q=80",
    badge: "РџСЂРѕРІРµСЂРµРЅ", city: "Р’Р°СЂРЅР°", price: "35 Р»РІ/С‡", eta: "РЎРІРѕР±РѕРґРµРЅ",
    tags: ["РџР°СЂРєРµС‚", "Р›Р°РјРёРЅР°С‚", "РЁРїР°РєР»РѕРІРєР°", "Р›Р°Рє"], verified: true, online: false,
  },
  {
    id: 6, name: "РџРµС‚СЉСЂ Р•Р»РµРєС‚СЂРёРє", specialty: "Р•Р»РµРєС‚СЂРѕРёРЅСЃС‚Р°Р»Р°С†РёРё", rating: 4.8, reviews: 78, jobs: 145,
    img: "https://images.unsplash.com/photo-1774600166588-1db444bda799?w=300&q=80",
    badge: "РўРѕРї РёР·РїСЉР»РЅРёС‚РµР»", city: "РЎРѕС„РёСЏ", price: "55 Р»РІ/С‡", eta: "РЎРІРѕР±РѕРґРµРЅ СЃРµРіР°",
    tags: ["РўР°Р±Р»o", "РРЅСЃС‚Р°Р»Р°С†РёРё", "РљР»РёРјР°С‚РёРє", "РћСЃРІРµС‚Р»РµРЅРёРµ"], verified: true, online: true,
  },
];

const CATEGORIES = ["Р’СЃРёС‡РєРё", "Р’РёРљ", "РЎС‚СЂРѕРёС‚РµР»СЃС‚РІРѕ", "Р•Р»РµРєС‚СЂРѕ", "Р”РёР·Р°Р№РЅ", "Р”РѕРіСЂР°РјР°", "РџР°СЂРєРµС‚"];

const BADGE_STYLE: Record<string, string> = {
  "РўРѕРї РёР·РїСЉР»РЅРёС‚РµР»": "bg-amber-50 text-amber-700 border-amber-200",
  "РџСЂРѕРІРµСЂРµРЅ": "bg-teal-50 text-teal-700 border-teal-200",
  "Р¤РёСЂРјР°": "bg-blue-50 text-blue-700 border-blue-200",
};

export function MarketplacePage() {
  const navigate = useNavigate();
  const [search, setSearch] = useState("");
  const [category, setCategory] = useState("Р’СЃРёС‡РєРё");
  const [saved, setSaved] = useState<number[]>([]);
  const [sortBy, setSortBy] = useState("rating");

  const filtered = PROS.filter(p =>
    (category === "Р’СЃРёС‡РєРё" || p.tags.some(t => t.toLowerCase().includes(category.toLowerCase()))) &&
    (p.name.toLowerCase().includes(search.toLowerCase()) || p.specialty.toLowerCase().includes(search.toLowerCase()) || p.city.toLowerCase().includes(search.toLowerCase()))
  ).sort((a, b) => {
    if (sortBy === "rating") return b.rating - a.rating;
    if (sortBy === "jobs") return b.jobs - a.jobs;
    return 0;
  });

  return (
    <div className="p-5 lg:p-8">
      {/* Header */}
      <div className="mb-6">
        <h1 className="text-gray-800 mb-1">РџР°Р·Р°СЂ РЅР° РёР·РїСЉР»РЅРёС‚РµР»Рё</h1>
        <p className="text-sm text-gray-400">РќР°РјРµСЂРµС‚Рµ РїСЂРѕРІРµСЂРµРЅ РјР°Р№СЃС‚РѕСЂ Р·Р° РІР°С€РёСЏ РїСЂРѕРµРєС‚</p>
      </div>

      {/* Stats banner */}
      <div className="grid grid-cols-3 gap-3 mb-6">
        {[
          { icon: ShieldCheck, v: "500+", l: "Р’РµСЂРёС„РёС†РёСЂР°РЅРё",  c: "text-teal-600", bg: "bg-teal-50" },
          { icon: CheckCircle2, v: "98%",  l: "Р’ СЃСЂРѕРє",       c: "text-green-600", bg: "bg-green-50" },
          { icon: Star,        v: "4.8в…", l: "РЎСЂРµРґРЅР° РѕС†РµРЅРєР°", c: "text-amber-600", bg: "bg-amber-50" },
        ].map((s, i) => (
          <div key={i} className="bg-white rounded-2xl border border-gray-100 px-3 py-3 flex items-center gap-2.5 shadow-sm">
            <div className={`size-8 rounded-xl ${s.bg} flex items-center justify-center flex-shrink-0`}>
              <s.icon className={`size-4 ${s.c}`} />
            </div>
            <div>
              <p className={`text-sm font-semibold ${s.c}`}>{s.v}</p>
              <p className="text-xs text-gray-400">{s.l}</p>
            </div>
          </div>
        ))}
      </div>

      {/* Search + filters */}
      <div className="flex flex-col sm:flex-row gap-3 mb-5">
        <div className="relative flex-1">
          <Search className="absolute left-3.5 top-1/2 -translate-y-1/2 size-4 text-gray-400 pointer-events-none" />
          <input placeholder="РўСЉСЂСЃРё РјР°Р№СЃС‚РѕСЂ, СЃРїРµС†РёР°Р»РЅРѕСЃС‚ РёР»Рё РіСЂР°РґвЂ¦" value={search} onChange={e => setSearch(e.target.value)}
            className="w-full pl-10 pr-4 py-2.5 bg-white border border-gray-200 rounded-xl text-sm text-gray-800 placeholder-gray-400 focus:outline-none focus:ring-2 focus:ring-blue-500/20 focus:border-blue-400 transition-all" />
        </div>
        <div className="relative">
          <select value={sortBy} onChange={e => setSortBy(e.target.value)}
            className="appearance-none pl-4 pr-8 py-2.5 bg-white border border-gray-200 rounded-xl text-sm text-gray-700 focus:outline-none focus:ring-2 focus:ring-blue-500/20 cursor-pointer">
            <option value="rating">РџРѕ РѕС†РµРЅРєР°</option>
            <option value="jobs">РџРѕ РїСЂРѕРµРєС‚Рё</option>
          </select>
          <ChevronDown className="absolute right-2.5 top-1/2 -translate-y-1/2 size-4 text-gray-400 pointer-events-none" />
        </div>
      </div>

      {/* Categories */}
      <div className="flex gap-2 overflow-x-auto pb-1 mb-6 scrollbar-none" style={{ scrollbarWidth: "none" }}>
        {CATEGORIES.map(c => (
          <button key={c} onClick={() => setCategory(c)}
            className={`flex-shrink-0 px-4 py-2 rounded-xl text-sm transition-all
              ${category === c ? "bg-blue-600 text-white shadow-md shadow-blue-200" : "bg-white text-gray-600 border border-gray-200 hover:border-blue-200"}`}>
            {c}
          </button>
        ))}
      </div>

      {/* Pros grid */}
      <div className="grid grid-cols-1 sm:grid-cols-2 xl:grid-cols-3 gap-4">
        {filtered.map(pro => (
          <div key={pro.id} className="group bg-white rounded-2xl border border-gray-100 overflow-hidden shadow-sm hover:shadow-xl hover:border-blue-100 transition-all duration-300">
            {/* Top image strip */}
            <div className="relative h-36 overflow-hidden">
              <img src={pro.img} alt={pro.name} className="w-full h-full object-cover object-top group-hover:scale-105 transition-transform duration-500" />
              <div className="absolute inset-0 bg-gradient-to-t from-black/60 to-transparent" />
              <div className="absolute top-3 left-3 flex gap-2">
                <span className={`px-2.5 py-1 rounded-full text-xs border flex items-center gap-1 bg-white/95 ${BADGE_STYLE[pro.badge] || "bg-gray-50 text-gray-700 border-gray-200"}`}>
                  <ShieldCheck className="size-3" />{pro.badge}
                </span>
              </div>
              <button onClick={() => setSaved(s => s.includes(pro.id) ? s.filter(i => i !== pro.id) : [...s, pro.id])}
                className="absolute top-3 right-3 size-8 rounded-full bg-white/90 flex items-center justify-center hover:bg-white transition-colors shadow-sm">
                <Heart className={`size-4 ${saved.includes(pro.id) ? "text-red-500 fill-red-500" : "text-gray-400"}`} />
              </button>
              {pro.online && (
                <div className="absolute bottom-3 right-3 flex items-center gap-1.5 px-2.5 py-1 rounded-full bg-green-500/90 backdrop-blur-sm">
                  <span className="size-1.5 rounded-full bg-white animate-pulse" />
                  <span className="text-white text-xs">РћРЅР»Р°Р№РЅ</span>
                </div>
              )}
            </div>

            <div className="p-4">
              <div className="flex items-start justify-between mb-2">
                <div>
                  <p className="text-sm text-gray-800">{pro.name}</p>
                  <p className="text-xs text-gray-500">{pro.specialty}</p>
                </div>
                <div className="flex items-center gap-1 flex-shrink-0">
                  <Star className="size-3.5 text-amber-400 fill-amber-400" />
                  <span className="text-sm text-gray-800">{pro.rating}</span>
                  <span className="text-xs text-gray-400">({pro.reviews})</span>
                </div>
              </div>

              <div className="flex items-center gap-3 text-xs text-gray-500 mb-3">
                <span className="flex items-center gap-1"><MapPin className="size-3 text-gray-400" />{pro.city}</span>
                <span className="flex items-center gap-1"><CheckCircle2 className="size-3 text-teal-500" />{pro.jobs} РїСЂРѕРµРєС‚Р°</span>
              </div>

              {/* Tags */}
              <div className="flex flex-wrap gap-1.5 mb-3">
                {pro.tags.slice(0, 3).map(t => (
                  <span key={t} className="px-2 py-0.5 rounded-lg bg-gray-100 text-gray-600 text-xs">{t}</span>
                ))}
              </div>

              <div className="flex items-center justify-between pt-3 border-t border-gray-50">
                <div>
                  <p className="text-sm text-blue-700 font-medium">{pro.price}</p>
                  <p className="text-xs text-gray-400 flex items-center gap-1 mt-0.5">
                    <Clock className="size-3" />{pro.eta}
                  </p>
                </div>
                <div className="flex gap-2">
                  <button onClick={() => navigate("/client/chat")}
                    className="size-9 flex items-center justify-center rounded-xl bg-gray-100 text-gray-600 hover:bg-gray-200 transition-colors">
                    <MessageSquare className="size-4" />
                  </button>
                  <button className="flex items-center gap-1.5 px-3.5 py-2 rounded-xl bg-blue-600 text-white text-xs hover:bg-blue-700 transition-colors shadow-sm shadow-blue-200">
                    <Zap className="size-3.5" />
                    РџРѕСЂСЉС‡Р°Р№
                  </button>
                </div>
              </div>
            </div>
          </div>
        ))}
      </div>
    </div>
  );
}



// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ
// FILE: src/app/pages/client/DocumentsPage.tsx
// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ

import { useState } from "react";
import {
  FileText, Download, Eye, Trash2, Upload, Search,
  Filter, CheckCircle2, Clock, AlertCircle, Plus,
  FileSignature, FileSpreadsheet, FileBadge, MoreHorizontal,
} from "lucide-react";

const DOCS = [
  {
    id: 1, name: "Р”РѕРіРѕРІРѕСЂ вЂ” Р РµРјРѕРЅС‚ Р±Р°РЅСЏ СѓР». Р’РёС‚РѕС€Р° 12", type: "contract",
    date: "22 РјР°СЂ 2026", size: "245 KB", status: "signed",
    project: "Р РµРјРѕРЅС‚ Р±Р°РЅСЏ", party: "Р“РµРѕСЂРіРё РЎС‚СЂРѕРµРІ",
  },
  {
    id: 2, name: "РљРЎРЎ вЂ” Р РµРјРѕРЅС‚ Р±Р°РЅСЏ (РјР°С‚РµСЂРёР°Р»Рё + С‚СЂСѓРґ)", type: "ks",
    date: "20 РјР°СЂ 2026", size: "88 KB", status: "active",
    project: "Р РµРјРѕРЅС‚ Р±Р°РЅСЏ", party: "Р“РµРѕСЂРіРё РЎС‚СЂРѕРµРІ",
  },
  {
    id: 3, name: "РћС„РµСЂС‚Р° вЂ” Р‘РѕСЏРґРёСЃРІР°РЅРµ С…РѕР» Рё РєСѓС…РЅСЏ", type: "offer",
    date: "2 Р°РїСЂ 2026", size: "120 KB", status: "pending",
    project: "Р‘РѕСЏРґРёСЃРІР°РЅРµ С…РѕР»", party: "3 РѕС„РµСЂС‚Рё",
  },
  {
    id: 4, name: "Р¤Р°РєС‚СѓСЂР° в„–00234 вЂ” Р’РёРљ РєСѓС…РЅСЏ", type: "invoice",
    date: "28 РјР°СЂ 2026", size: "65 KB", status: "paid",
    project: "Р’РёРљ РєСѓС…РЅСЏ", party: "РњР°СЂС‚РёРЅ Р”РёРјРёС‚СЂРѕРІ",
  },
  {
    id: 5, name: "Р”РѕРіРѕРІРѕСЂ вЂ” РЎРјСЏРЅР° РґРѕРіСЂР°РјР° 4 РїСЂРѕР·РѕСЂРµС†Р°", type: "contract",
    date: "10 С„РµРІ 2026", size: "310 KB", status: "signed",
    project: "Р”РѕРіСЂР°РјР°", party: "РЎС‚СЂРѕР№ РџР»СЋСЃ РћРћР”",
  },
  {
    id: 6, name: "РћС„РµСЂС‚Р° вЂ” Р›Р°РјРёРЅРёСЂР°РЅ РїР°СЂРєРµС‚ СЃРїР°Р»РЅСЏ", type: "offer",
    date: "30 РјР°СЂ 2026", size: "95 KB", status: "active",
    project: "РџР°СЂРєРµС‚ СЃРїР°Р»РЅСЏ", party: "РРІР°РЅ РџР°СЂРєРµС‚РѕРІ",
  },
  {
    id: 7, name: "Р“Р°СЂР°РЅС†РёРѕРЅРЅР° РєР°СЂС‚Р° вЂ” Р”РѕРіСЂР°РјР°", type: "warranty",
    date: "15 РјР°СЂ 2026", size: "42 KB", status: "active",
    project: "Р”РѕРіСЂР°РјР°", party: "РЎС‚СЂРѕР№ РџР»СЋСЃ РћРћР”",
  },
];

const TYPE_META: Record<string, { icon: typeof FileText; label: string; color: string; bg: string }> = {
  contract: { icon: FileSignature,   label: "Р”РѕРіРѕРІРѕСЂ",   color: "text-blue-600",   bg: "bg-blue-50" },
  ks:       { icon: FileSpreadsheet, label: "РљРЎРЎ",       color: "text-violet-600", bg: "bg-violet-50" },
  offer:    { icon: FileBadge,       label: "РћС„РµСЂС‚Р°",    color: "text-teal-600",   bg: "bg-teal-50" },
  invoice:  { icon: FileText,        label: "Р¤Р°РєС‚СѓСЂР°",   color: "text-amber-600",  bg: "bg-amber-50" },
  warranty: { icon: FileBadge,       label: "Р“Р°СЂР°РЅС†РёСЏ",  color: "text-green-600",  bg: "bg-green-50" },
};

const STATUS_META: Record<string, { label: string; cls: string; icon: typeof Clock }> = {
  signed:  { label: "РџРѕРґРїРёСЃР°РЅ",  cls: "bg-green-50 text-green-700 border-green-200",  icon: CheckCircle2 },
  active:  { label: "РђРєС‚РёРІРµРЅ",   cls: "bg-blue-50 text-blue-700 border-blue-200",    icon: CheckCircle2 },
  pending: { label: "Р§Р°РєР°",      cls: "bg-amber-50 text-amber-700 border-amber-200", icon: AlertCircle },
  paid:    { label: "РџР»Р°С‚РµРЅ",    cls: "bg-teal-50 text-teal-700 border-teal-200",    icon: CheckCircle2 },
};

const FILTER_TABS = [
  { key: "all",      label: "Р’СЃРёС‡РєРё" },
  { key: "contract", label: "Р”РѕРіРѕРІРѕСЂРё" },
  { key: "offer",    label: "РћС„РµСЂС‚Рё" },
  { key: "ks",       label: "РљРЎРЎ" },
  { key: "invoice",  label: "Р¤Р°РєС‚СѓСЂРё" },
];

export function DocumentsPage() {
  const [search, setSearch] = useState("");
  const [filter, setFilter] = useState("all");
  const [previewId, setPreviewId] = useState<number | null>(null);

  const filtered = DOCS.filter(d =>
    (filter === "all" || d.type === filter) &&
    (d.name.toLowerCase().includes(search.toLowerCase()) || d.project.toLowerCase().includes(search.toLowerCase()))
  );

  const preview = DOCS.find(d => d.id === previewId);

  return (
    <div className="p-5 lg:p-8">
      {/* Header */}
      <div className="flex items-center justify-between mb-6">
        <div>
          <h1 className="text-gray-800">Р”РѕРєСѓРјРµРЅС‚Рё</h1>
          <p className="text-sm text-gray-400">{DOCS.length} РґРѕРєСѓРјРµРЅС‚Р° вЂў РґРѕРіРѕРІРѕСЂРё, РѕС„РµСЂС‚Рё, С„Р°РєС‚СѓСЂРё</p>
        </div>
        <button className="flex items-center gap-2 px-4 py-2.5 rounded-xl bg-blue-600 text-white text-sm hover:bg-blue-700 transition-all shadow-md shadow-blue-200 active:scale-95">
          <Upload className="size-4" />
          <span className="hidden sm:inline">РљР°С‡Рё РґРѕРєСѓРјРµРЅС‚</span>
        </button>
      </div>

      {/* Stats */}
      <div className="grid grid-cols-2 sm:grid-cols-4 gap-3 mb-6">
        {[
          { label: "Р”РѕРіРѕРІРѕСЂРё",  v: DOCS.filter(d => d.type === "contract").length, icon: FileSignature,   color: "text-blue-600",   bg: "bg-blue-50" },
          { label: "РћС„РµСЂС‚Рё",    v: DOCS.filter(d => d.type === "offer").length,    icon: FileBadge,       color: "text-teal-600",   bg: "bg-teal-50" },
          { label: "РљРЎРЎ",       v: DOCS.filter(d => d.type === "ks").length,       icon: FileSpreadsheet, color: "text-violet-600", bg: "bg-violet-50" },
          { label: "Р¤Р°РєС‚СѓСЂРё",   v: DOCS.filter(d => d.type === "invoice").length,  icon: FileText,        color: "text-amber-600",  bg: "bg-amber-50" },
        ].map(s => (
          <div key={s.label} className="bg-white rounded-2xl border border-gray-100 p-3.5 flex items-center gap-3 shadow-sm">
            <div className={`size-8 rounded-xl ${s.bg} flex items-center justify-center flex-shrink-0`}>
              <s.icon className={`size-4 ${s.color}`} />
            </div>
            <div>
              <p className={`text-lg font-semibold ${s.color}`}>{s.v}</p>
              <p className="text-xs text-gray-400">{s.label}</p>
            </div>
          </div>
        ))}
      </div>

      {/* Search + Filter */}
      <div className="flex flex-col sm:flex-row gap-3 mb-4">
        <div className="relative flex-1">
          <Search className="absolute left-3.5 top-1/2 -translate-y-1/2 size-4 text-gray-400 pointer-events-none" />
          <input placeholder="РўСЉСЂСЃРё РґРѕРєСѓРјРµРЅС‚ РёР»Рё РїСЂРѕРµРєС‚вЂ¦" value={search} onChange={e => setSearch(e.target.value)}
            className="w-full pl-10 pr-4 py-2.5 bg-white border border-gray-200 rounded-xl text-sm text-gray-800 placeholder-gray-400 focus:outline-none focus:ring-2 focus:ring-blue-500/20 focus:border-blue-400 transition-all" />
        </div>
      </div>

      {/* Tabs */}
      <div className="flex gap-2 overflow-x-auto pb-1 mb-5" style={{ scrollbarWidth: "none" }}>
        {FILTER_TABS.map(t => (
          <button key={t.key} onClick={() => setFilter(t.key)}
            className={`flex-shrink-0 px-3.5 py-2 rounded-xl text-xs transition-all
              ${filter === t.key ? "bg-blue-600 text-white shadow-md shadow-blue-200" : "bg-white text-gray-600 border border-gray-200 hover:border-blue-200"}`}>
            {t.label}
          </button>
        ))}
      </div>

      <div className="flex gap-5">
        {/* Documents list */}
        <div className={`flex-1 min-w-0 space-y-2 ${previewId ? "hidden lg:block" : ""}`}>
          {filtered.length === 0 ? (
            <div className="bg-white rounded-2xl border border-gray-100 p-12 text-center">
              <FileText className="size-10 text-gray-200 mx-auto mb-3" />
              <p className="text-sm text-gray-400">РќСЏРјР° РЅР°РјРµСЂРµРЅРё РґРѕРєСѓРјРµРЅС‚Рё</p>
            </div>
          ) : filtered.map(doc => {
            const tm = TYPE_META[doc.type] || TYPE_META.contract;
            const sm = STATUS_META[doc.status] || STATUS_META.active;
            const Icon = tm.icon;
            const StatusIcon = sm.icon;
            return (
              <div key={doc.id}
                className={`group bg-white rounded-2xl border transition-all cursor-pointer hover:shadow-md
                  ${previewId === doc.id ? "border-blue-300 shadow-md shadow-blue-50" : "border-gray-100 hover:border-gray-200"}`}
                onClick={() => setPreviewId(previewId === doc.id ? null : doc.id)}>
                <div className="p-4 flex items-center gap-4">
                  <div className={`size-11 rounded-2xl ${tm.bg} flex items-center justify-center flex-shrink-0`}>
                    <Icon className={`size-5 ${tm.color}`} />
                  </div>
                  <div className="flex-1 min-w-0">
                    <div className="flex items-start justify-between gap-2 mb-1">
                      <p className="text-sm text-gray-800 leading-snug truncate">{doc.name}</p>
                      <span className={`flex items-center gap-1 px-2 py-0.5 rounded-lg text-xs border flex-shrink-0 ${sm.cls}`}>
                        <StatusIcon className="size-3" />{sm.label}
                      </span>
                    </div>
                    <div className="flex items-center gap-3 text-xs text-gray-400">
                      <span className={`px-1.5 py-0.5 rounded-md text-xs ${tm.bg} ${tm.color}`}>{tm.label}</span>
                      <span>{doc.project}</span>
                      <span>{doc.date}</span>
                      <span>{doc.size}</span>
                    </div>
                  </div>
                  <div className="flex items-center gap-1 opacity-0 group-hover:opacity-100 transition-opacity">
                    <button onClick={e => { e.stopPropagation(); }} className="size-8 flex items-center justify-center rounded-lg hover:bg-blue-50 text-gray-400 hover:text-blue-600 transition-colors">
                      <Eye className="size-4" />
                    </button>
                    <button onClick={e => { e.stopPropagation(); }} className="size-8 flex items-center justify-center rounded-lg hover:bg-gray-100 text-gray-400 transition-colors">
                      <Download className="size-4" />
                    </button>
                    <button onClick={e => { e.stopPropagation(); }} className="size-8 flex items-center justify-center rounded-lg hover:bg-red-50 text-gray-400 hover:text-red-500 transition-colors">
                      <Trash2 className="size-4" />
                    </button>
                  </div>
                </div>
              </div>
            );
          })}

          {/* Upload zone */}
          <div className="border-2 border-dashed border-gray-200 rounded-2xl p-8 text-center hover:border-blue-300 hover:bg-blue-50/50 transition-all cursor-pointer group">
            <div className="size-12 rounded-2xl bg-gray-100 group-hover:bg-blue-100 flex items-center justify-center mx-auto mb-3 transition-colors">
              <Plus className="size-6 text-gray-400 group-hover:text-blue-500" />
            </div>
            <p className="text-sm text-gray-500 group-hover:text-blue-700 transition-colors">РљР°С‡РµС‚Рµ РёР»Рё РїР»СЉР·РЅРµС‚Рµ РґРѕРєСѓРјРµРЅС‚ С‚СѓРє</p>
            <p className="text-xs text-gray-400 mt-1">PDF, DOC, DOCX, XLS вЂ” РґРѕ 10 MB</p>
          </div>
        </div>

        {/* Preview panel */}
        {preview && (
          <div className="w-full lg:w-80 flex-shrink-0">
            <div className="bg-white rounded-2xl border border-blue-100 p-5 sticky top-4 shadow-md shadow-blue-50">
              <div className="flex items-center justify-between mb-4">
                <p className="text-sm text-gray-700">РџСЂРµРіР»РµРґ</p>
                <button onClick={() => setPreviewId(null)} className="text-xs text-gray-400 hover:text-gray-600">вњ•</button>
              </div>
              {(() => {
                const tm = TYPE_META[preview.type];
                const sm = STATUS_META[preview.status];
                const Icon = tm.icon;
                return (
                  <>
                    <div className={`size-16 rounded-2xl ${tm.bg} flex items-center justify-center mx-auto mb-4`}>
                      <Icon className={`size-8 ${tm.color}`} />
                    </div>
                    <h3 className="text-sm text-gray-800 text-center mb-4 leading-snug">{preview.name}</h3>
                    <div className="space-y-2.5 mb-5">
                      {[
                        ["РўРёРї", tm.label],
                        ["РџСЂРѕРµРєС‚", preview.project],
                        ["РЎС‚СЂР°РЅР°", preview.party],
                        ["Р”Р°С‚Р°", preview.date],
                        ["Р Р°Р·РјРµСЂ", preview.size],
                        ["РЎС‚Р°С‚СѓСЃ", sm.label],
                      ].map(([k, v]) => (
                        <div key={k} className="flex justify-between">
                          <span className="text-xs text-gray-400">{k}</span>
                          <span className="text-xs text-gray-700">{v}</span>
                        </div>
                      ))}
                    </div>
                    <div className="space-y-2">
                      <button className="w-full flex items-center justify-center gap-2 py-2.5 rounded-xl bg-blue-600 text-white text-xs hover:bg-blue-700 transition-colors shadow-sm shadow-blue-200">
                        <Eye className="size-3.5" />РћС‚РІРѕСЂРё РґРѕРєСѓРјРµРЅС‚Р°
                      </button>
                      <button className="w-full flex items-center justify-center gap-2 py-2.5 rounded-xl bg-gray-100 text-gray-700 text-xs hover:bg-gray-200 transition-colors">
                        <Download className="size-3.5" />РР·С‚РµРіР»Рё
                      </button>
                    </div>
                  </>
                );
              })()}
            </div>
          </div>
        )}
      </div>
    </div>
  );
}



// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ
// FILE: src/app/pages/client/CommunityPage.tsx
// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ

import { useState } from "react";
import { Play, Heart, Eye, MessageCircle, Search, TrendingUp, BookmarkPlus, Share2 } from "lucide-react";

const CATEGORIES = ["Р’СЃРёС‡РєРё", "Р‘Р°РЅСЏ", "РљСѓС…РЅСЏ", "РҐРѕР»", "РџРѕРґРѕРІРё", "Р¤Р°СЃР°РґР°", "РЎС‚СЂРѕРёС‚РµР»СЃС‚РІРѕ", "Р”РёР·Р°Р№РЅ"];

const VIDEOS = [
  {
    id: 1, title: "Р РµРјРѕРЅС‚ РЅР° Р±Р°РЅСЏ Р·Р° 10 РґРЅРё вЂ” РїСЉР»РµРЅ РїСЂРѕС†РµСЃ", channel: "РЎС‚СЂРѕР№ РњР°Р№СЃС‚РѕСЂ", views: "12.4K",
    likes: "843", comments: 67, duration: "3:24", tag: "Р‘Р°РЅСЏ", featured: true,
    img: "https://images.unsplash.com/photo-1612153284972-7e80a48abcb9?w=800&q=80",
    avatar: "https://images.unsplash.com/photo-1728516687003-58347d3412b3?w=60&q=80",
    desc: "РџСЉР»РµРЅ РїСЂРѕС†РµСЃ РЅР° СЂРµРјРѕРЅС‚ вЂ” РѕС‚ РґРµРјРѕРЅС‚Р°Р¶ РґРѕ С„РёРЅР°Р»РЅРѕ РїРѕС‡РёСЃС‚РІР°РЅРµ",
  },
  {
    id: 2, title: "РљСѓС…РЅСЏ РѕС‚ РЅСѓР»Р°С‚Р° вЂ” РїСЂРµРґРё Рё СЃР»РµРґ С‚СЂР°РЅСЃС„РѕСЂРјР°С†РёСЏ", channel: "Interior BG", views: "8.7K",
    likes: "621", comments: 44, duration: "5:11", tag: "РљСѓС…РЅСЏ", featured: true,
    img: "https://images.unsplash.com/photo-1771862956702-4e8b247e28b5?w=800&q=80",
    avatar: "https://images.unsplash.com/photo-1770058428154-9eee8a6a1fbb?w=60&q=80",
    desc: "РљР°Рє РїСЂРµРІСЉСЂРЅР°С…РјРµ РѕСЃС‚Р°СЂСЏР»Р°С‚Р° РєСѓС…РЅСЏ РІ РјРѕРґРµСЂРЅР° вЂ” Р±СЋРґР¶РµС‚ 12 000 Р»РІ",
  },
  {
    id: 3, title: "РџРѕСЃС‚Р°РІСЏРЅРµ РЅР° Р»Р°РјРёРЅРёСЂР°РЅ РїР°СЂРєРµС‚ СЃС‚СЉРїРєР° РїРѕ СЃС‚СЉРїРєР°", channel: "РџР°СЂРєРµС‚ РџСЂРѕ", views: "5.2K",
    likes: "398", comments: 31, duration: "2:47", tag: "РџРѕРґРѕРІРё", featured: false,
    img: "https://images.unsplash.com/photo-1636200534256-c08268363482?w=800&q=80",
    avatar: "https://images.unsplash.com/photo-1621905252472-943afaa20e20?w=60&q=80",
    desc: "Р’СЃРёС‡РєРѕ Р·Р° РїСЂР°РІРёР»РЅРѕС‚Рѕ РїРѕСЃС‚Р°РІСЏРЅРµ вЂ” РёРЅСЃС‚СЂСѓРјРµРЅС‚Рё, С‚РµС…РЅРёРєРё, РіСЂРµС€РєРё",
  },
  {
    id: 4, title: "РњРѕРґРµСЂРµРЅ С…РѕР» СЃ РјРёРЅРёРјР°Р»РёСЃС‚РёС‡РµРЅ РґРёР·Р°Р№РЅ", channel: "DesignSpace BG", views: "9.1K",
    likes: "712", comments: 58, duration: "4:02", tag: "РҐРѕР»", featured: false,
    img: "https://images.unsplash.com/photo-1760072513442-9872656c1b07?w=800&q=80",
    avatar: "https://images.unsplash.com/photo-1770058428154-9eee8a6a1fbb?w=60&q=80",
    desc: "РљР°Рє РґР° РїРѕСЃС‚РёРіРЅРµС‚Рµ СЃРєР°РЅРґРёРЅР°РІСЃРєРё СЃС‚РёР» СЃ РјР°Р»РєРѕ РїР°СЂРё",
  },
  {
    id: 5, title: "РР·РіСЂР°Р¶РґР°РЅРµ РЅР° С„Р°СЃР°РґР° СЃ С‚РѕРїР»РѕРёР·РѕР»Р°С†РёСЏ", channel: "РЎС‚СЂРѕР№ РџР»СЋСЃ", views: "6.3K",
    likes: "445", comments: 29, duration: "7:15", tag: "Р¤Р°СЃР°РґР°", featured: false,
    img: "https://images.unsplash.com/photo-1774600166588-1db444bda799?w=800&q=80",
    avatar: "https://images.unsplash.com/photo-1627660080110-20045fd3875d?w=60&q=80",
    desc: "РЎС‚СЉРїРєРё Р·Р° РїСЂР°РІРёР»РЅР° С‚РѕРїР»РѕРёР·РѕР»Р°С†РёСЏ вЂ” СЃРїРµСЃС‚РµС‚Рµ РґРѕ 40% РѕС‚ РїР°СЂРЅРѕС‚Рѕ",
  },
  {
    id: 6, title: "SPA Р±Р°РЅСЏ Р·Р° 15 000 Р»РІ вЂ” СЂРµР°Р»РёР·Р°С†РёСЏ", channel: "BathPro", views: "14.2K",
    likes: "1.1K", comments: 92, duration: "6:34", tag: "Р‘Р°РЅСЏ", featured: false,
    img: "https://images.unsplash.com/photo-1649719742478-830ba2e55b5d?w=800&q=80",
    avatar: "https://images.unsplash.com/photo-1728516687003-58347d3412b3?w=60&q=80",
    desc: "Р›СѓРєСЃРѕР·РЅР° Р±Р°РЅСЏ СЃ РїРѕРґРѕРІРѕ РѕС‚РѕРїР»РµРЅРёРµ Рё РґСЉР¶РґРѕРІРµРЅ РґСѓС€",
  },
];

function VideoCard({ video, big = false }: { video: typeof VIDEOS[0]; big?: boolean }) {
  const [playing, setPlaying] = useState(false);
  const [liked, setLiked] = useState(false);
  const [saved, setSaved] = useState(false);

  if (big) {
    return (
      <div className="bg-white rounded-2xl border border-gray-100 overflow-hidden shadow-sm hover:shadow-lg transition-all">
        <div className="relative overflow-hidden cursor-pointer" style={{ height: 260 }} onClick={() => setPlaying(!playing)}>
          <img src={video.img} alt={video.title} className="w-full h-full object-cover hover:scale-105 transition-transform duration-500" />
          <div className="absolute inset-0 bg-gradient-to-t from-black/70 via-black/20 to-transparent" />
          <div className="absolute top-4 left-4">
            <span className="px-2.5 py-1 rounded-full bg-blue-600 text-white text-xs">{video.tag}</span>
          </div>
          <div className="absolute top-4 right-4">
            <span className="px-2.5 py-1 rounded-md bg-black/60 text-white text-xs">{video.duration}</span>
          </div>
          <div className="absolute inset-0 flex items-center justify-center">
            <div className={`size-16 rounded-full flex items-center justify-center transition-all duration-200
              ${playing ? "bg-white scale-110" : "bg-white/25 backdrop-blur-sm hover:bg-white/40 hover:scale-110"}`}>
              <Play className={`size-7 ml-1 ${playing ? "text-blue-600" : "text-white"}`} fill="currentColor" />
            </div>
          </div>
          <div className="absolute bottom-4 left-4 right-4">
            <h3 className="text-white text-base leading-snug mb-1">{video.title}</h3>
            <p className="text-white/70 text-xs">{video.desc}</p>
          </div>
        </div>
        <div className="p-4 flex items-center gap-3">
          <img src={video.avatar} alt="" className="size-8 rounded-full object-cover" />
          <div className="flex-1">
            <p className="text-xs text-gray-700">{video.channel}</p>
            <div className="flex items-center gap-3 text-xs text-gray-400 mt-0.5">
              <span className="flex items-center gap-1"><Eye className="size-3" />{video.views}</span>
              <span className="flex items-center gap-1"><MessageCircle className="size-3" />{video.comments}</span>
            </div>
          </div>
          <div className="flex items-center gap-1">
            <button onClick={() => setLiked(!liked)} className={`flex items-center gap-1.5 px-3 py-1.5 rounded-xl text-xs transition-all ${liked ? "bg-red-50 text-red-500" : "bg-gray-100 text-gray-500 hover:bg-red-50 hover:text-red-500"}`}>
              <Heart className={`size-3.5 ${liked ? "fill-red-500" : ""}`} />{video.likes}
            </button>
            <button onClick={() => setSaved(!saved)} className={`size-8 flex items-center justify-center rounded-xl transition-colors ${saved ? "bg-blue-50 text-blue-600" : "bg-gray-100 text-gray-500 hover:bg-blue-50 hover:text-blue-600"}`}>
              <BookmarkPlus className="size-4" />
            </button>
          </div>
        </div>
      </div>
    );
  }

  return (
    <div className="group bg-white rounded-2xl border border-gray-100 overflow-hidden shadow-sm hover:shadow-lg transition-all duration-300">
      <div className="relative overflow-hidden cursor-pointer h-40" onClick={() => setPlaying(!playing)}>
        <img src={video.img} alt={video.title} className="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500" />
        <div className="absolute inset-0 bg-gradient-to-t from-black/65 via-black/10 to-transparent" />
        <div className="absolute top-2.5 left-2.5">
          <span className="px-2 py-0.5 rounded-full bg-white/20 backdrop-blur-sm text-white text-xs border border-white/20">{video.tag}</span>
        </div>
        <div className="absolute top-2.5 right-2.5">
          <span className="px-2 py-0.5 rounded-md bg-black/50 text-white text-xs">{video.duration}</span>
        </div>
        <div className="absolute inset-0 flex items-center justify-center">
          <div className={`size-10 rounded-full flex items-center justify-center transition-all ${playing ? "bg-white scale-110" : "bg-white/25 backdrop-blur-sm group-hover:bg-white/40 group-hover:scale-110"}`}>
            <Play className={`size-4 ml-0.5 ${playing ? "text-blue-600" : "text-white"}`} fill="currentColor" />
          </div>
        </div>
        <div className="absolute bottom-2.5 left-2.5 right-2.5">
          <p className="text-white text-xs line-clamp-2 leading-tight">{video.title}</p>
        </div>
      </div>
      <div className="p-3 flex items-center gap-2">
        <img src={video.avatar} alt="" className="size-7 rounded-full object-cover flex-shrink-0" />
        <div className="flex-1 min-w-0">
          <p className="text-xs text-gray-600 truncate">{video.channel}</p>
          <div className="flex items-center gap-2 text-xs text-gray-400">
            <span className="flex items-center gap-0.5"><Eye className="size-3" />{video.views}</span>
            <span className="flex items-center gap-0.5"><Heart className="size-3" />{video.likes}</span>
          </div>
        </div>
        <button onClick={() => setLiked(!liked)} className={`size-7 flex items-center justify-center rounded-lg transition-colors ${liked ? "text-red-500" : "text-gray-400 hover:text-red-500"}`}>
          <Heart className={`size-4 ${liked ? "fill-red-500" : ""}`} />
        </button>
      </div>
    </div>
  );
}

export function CommunityPage() {
  const [category, setCategory] = useState("Р’СЃРёС‡РєРё");
  const [search, setSearch] = useState("");

  const featured = VIDEOS.filter(v => v.featured);
  const rest = VIDEOS.filter(v => {
    const matchCat = category === "Р’СЃРёС‡РєРё" || v.tag === category;
    const matchSearch = v.title.toLowerCase().includes(search.toLowerCase()) || v.channel.toLowerCase().includes(search.toLowerCase());
    return matchCat && matchSearch;
  });

  return (
    <div className="p-5 lg:p-8">
      {/* Header */}
      <div className="flex items-center gap-3 mb-6">
        <div className="size-10 rounded-2xl bg-gradient-to-br from-blue-600 to-teal-500 flex items-center justify-center shadow-md shadow-blue-200">
          <Play className="size-5 text-white ml-0.5" fill="white" />
        </div>
        <div>
          <h1 className="text-gray-800">Zclips</h1>
          <p className="text-sm text-gray-400">Р РµР°Р»РЅРё РїСЂРѕРµРєС‚Рё В· Р’РґСЉС…РЅРѕРІРµРЅРёРµ В· РЎСЉРІРµС‚Рё</p>
        </div>
      </div>

      {/* Search */}
      <div className="relative mb-5">
        <Search className="absolute left-4 top-1/2 -translate-y-1/2 size-4 text-gray-400 pointer-events-none" />
        <input placeholder="РўСЉСЂСЃРё РІРёРґРµРѕ, РєР°РЅР°Р» РёР»Рё С‚РµРјР°вЂ¦" value={search} onChange={e => setSearch(e.target.value)}
          className="w-full pl-11 pr-4 py-3 bg-white border border-gray-200 rounded-2xl text-sm text-gray-800 placeholder-gray-400 focus:outline-none focus:ring-2 focus:ring-blue-500/20 focus:border-blue-400 transition-all shadow-sm" />
      </div>

      {/* Trending banner */}
      {!search && category === "Р’СЃРёС‡РєРё" && (
        <div className="flex items-center gap-2 px-4 py-2.5 bg-gradient-to-r from-blue-50 to-teal-50 rounded-xl border border-blue-100 mb-5">
          <TrendingUp className="size-4 text-blue-500" />
          <span className="text-xs text-blue-700">РўР°Р·Рё СЃРµРґРјРёС†Р° вЂ” РЅР°Р№-РіР»РµРґР°РЅРё СЂРµРЅРѕРІР°С†РёРё РІ Р‘СЉР»РіР°СЂРёСЏ</span>
        </div>
      )}

      {/* Featured вЂ” top 2 */}
      {!search && category === "Р’СЃРёС‡РєРё" && (
        <div className="grid grid-cols-1 sm:grid-cols-2 gap-4 mb-8">
          {featured.map(v => <VideoCard key={v.id} video={v} big />)}
        </div>
      )}

      {/* Categories */}
      <div className="flex gap-2 overflow-x-auto pb-1 mb-5" style={{ scrollbarWidth: "none" }}>
        {CATEGORIES.map(c => (
          <button key={c} onClick={() => setCategory(c)}
            className={`flex-shrink-0 px-4 py-2 rounded-xl text-sm transition-all
              ${category === c ? "bg-blue-600 text-white shadow-md shadow-blue-200" : "bg-white text-gray-600 border border-gray-200 hover:border-blue-200"}`}>
            {c}
          </button>
        ))}
      </div>

      {/* All videos grid */}
      <div className="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-4">
        {rest.map(v => <VideoCard key={v.id} video={v} />)}
      </div>

      {rest.length === 0 && (
        <div className="bg-white rounded-2xl border border-gray-100 p-12 text-center">
          <Play className="size-10 text-gray-200 mx-auto mb-3" />
          <p className="text-sm text-gray-400">РќСЏРјР° РЅР°РјРµСЂРµРЅРё РІРёРґРµР°</p>
        </div>
      )}
    </div>
  );
}



// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ
// FILE: src/app/pages/client/SettingsPage.tsx
// в•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђв•ђ

import { useState } from "react";
import {
  User, Bell, Shield, Smartphone, Globe, LogOut,
  Camera, Check, ChevronRight, Eye, EyeOff, Trash2,
  Mail, Phone, MapPin, Building2,
} from "lucide-react";

const SECTIONS = [
  { key: "profile",   icon: User,       label: "РџСЂРѕС„РёР»" },
  { key: "notif",     icon: Bell,       label: "РР·РІРµСЃС‚РёСЏ" },
  { key: "security",  icon: Shield,     label: "РЎРёРіСѓСЂРЅРѕСЃС‚" },
  { key: "app",       icon: Smartphone, label: "РџСЂРёР»РѕР¶РµРЅРёРµ" },
];

function Toggle({ checked, onChange }: { checked: boolean; onChange: () => void }) {
  return (
    <button onClick={onChange}
      className={`relative w-11 h-6 rounded-full transition-colors flex-shrink-0 ${checked ? "bg-blue-600" : "bg-gray-200"}`}>
      <span className={`absolute top-0.5 left-0.5 size-5 rounded-full bg-white shadow-sm transition-transform ${checked ? "translate-x-5" : "translate-x-0"}`} />
    </button>
  );
}

export function SettingsPage() {
  const [section, setSection] = useState("profile");
  const [showPass, setShowPass] = useState(false);
  const [saved, setSaved] = useState(false);
  const [notifs, setNotifs] = useState({
    email: true, sms: false, push: true, weekly: true,
    offers: true, messages: true, updates: false,
  });
  const [profile, setProfile] = useState({
    name: "РРІР°РЅ РџРµС‚СЂРѕРІ", email: "ivan@example.com", phone: "+359 888 123 456",
    city: "РЎРѕС„РёСЏ", address: "СѓР». Р’РёС‚РѕС€Р° 12, РµС‚. 3",
  });

  const handleSave = () => {
    setSaved(true);
    setTimeout(() => setSaved(false), 2000);
  };

  return (
    <div className="p-5 lg:p-8 max-w-4xl mx-auto">
      <div className="mb-6">
        <h1 className="text-gray-800">РќР°СЃС‚СЂРѕР№РєРё</h1>
        <p className="text-sm text-gray-400">РЈРїСЂР°РІР»СЏРІР°Р№С‚Рµ РїСЂРѕС„РёР»Р° Рё РїСЂРµРґРїРѕС‡РёС‚Р°РЅРёСЏС‚Р° СЃРё</p>
      </div>

      <div className="flex flex-col sm:flex-row gap-5">
        {/* Sidebar nav */}
        <nav className="sm:w-52 flex-shrink-0">
          <div className="bg-white rounded-2xl border border-gray-100 overflow-hidden shadow-sm">
            {/* Avatar section */}
            <div className="p-5 text-center border-b border-gray-50">
              <div className="relative inline-block mb-3">
                <div className="size-16 rounded-full bg-gradient-to-br from-blue-500 to-teal-500 flex items-center justify-center text-white text-xl mx-auto">
                  РРџ
                </div>
                <button className="absolute bottom-0 right-0 size-6 rounded-full bg-blue-600 flex items-center justify-center shadow-md hover:bg-blue-700 transition-colors">
                  <Camera className="size-3 text-white" />
                </button>
              </div>
              <p className="text-sm text-gray-800">{profile.name}</p>
              <p className="text-xs text-gray-400">РљР»РёРµРЅС‚</p>
            </div>

            {/* Nav items */}
            <div className="p-2">
              {SECTIONS.map(s => (
                <button key={s.key} onClick={() => setSection(s.key)}
                  className={`w-full flex items-center gap-3 px-3 py-2.5 rounded-xl text-left transition-all mb-0.5
                    ${section === s.key ? "bg-blue-50 text-blue-700" : "text-gray-600 hover:bg-gray-50"}`}>
                  <s.icon className={`size-4 flex-shrink-0 ${section === s.key ? "text-blue-600" : "text-gray-400"}`} />
                  <span className="text-sm">{s.label}</span>
                  {section === s.key && <ChevronRight className="size-3.5 text-blue-400 ml-auto" />}
                </button>
              ))}
            </div>

            <div className="p-2 border-t border-gray-50">
              <button className="w-full flex items-center gap-3 px-3 py-2.5 rounded-xl text-red-500 hover:bg-red-50 transition-colors">
                <LogOut className="size-4" />
                <span className="text-sm">РР·С…РѕРґ</span>
              </button>
            </div>
          </div>
        </nav>

        {/* Content */}
        <div className="flex-1 min-w-0">

          {/* в”Ђв”Ђ Profile в”Ђв”Ђ */}
          {section === "profile" && (
            <div className="bg-white rounded-2xl border border-gray-100 shadow-sm overflow-hidden">
              <div className="px-6 py-4 border-b border-gray-50">
                <h2 className="text-gray-800">Р›РёС‡РЅРё РґР°РЅРЅРё</h2>
                <p className="text-xs text-gray-400">РџСЂРѕРјРµРЅРёС‚Рµ СЃРµ Р·Р°РїР°Р·РІР°С‚ Р°РІС‚РѕРјР°С‚РёС‡РЅРѕ</p>
              </div>
              <div className="p-6 space-y-4">
                <div className="grid grid-cols-1 sm:grid-cols-2 gap-4">
                  {[
                    { icon: User,     label: "РџСЉР»РЅРѕ РёРјРµ",   key: "name",    ph: "Р’Р°С€РµС‚Рѕ ime" },
                    { icon: Mail,     label: "РРјРµР№Р»",        key: "email",   ph: "example@mail.com" },
                    { icon: Phone,    label: "РўРµР»РµС„РѕРЅ",      key: "phone",   ph: "+359 8XX XXX XXX" },
                    { icon: MapPin,   label: "Р“СЂР°Рґ",         key: "city",    ph: "РЎРѕС„РёСЏ" },
                  ].map(f => (
                    <div key={f.key}>
                      <label className="block text-sm text-gray-700 mb-1.5">{f.label}</label>
                      <div className="relative">
                        <f.icon className="absolute left-3.5 top-1/2 -translate-y-1/2 size-4 text-gray-400 pointer-events-none" />
                        <input type="text" placeholder={f.ph} value={profile[f.key as keyof typeof profile]}
                          onChange={e => setProfile(p => ({ ...p, [f.key]: e.target.value }))}
                          className="w-full pl-10 pr-4 py-2.5 bg-gray-50 border border-gray-200 rounded-xl text-sm text-gray-800 placeholder-gray-400 focus:outline-none focus:ring-2 focus:ring-blue-500/20 focus:border-blue-400 transition-all" />
                      </div>
                    </div>
                  ))}
                </div>
                <div>
                  <label className="block text-sm text-gray-700 mb-1.5">РђРґСЂРµСЃ</label>
                  <div className="relative">
                    <Building2 className="absolute left-3.5 top-3 size-4 text-gray-400 pointer-events-none" />
                    <input type="text" placeholder="СѓР»., РЅРѕРјРµСЂ, РµС‚Р°Р¶" value={profile.address}
                      onChange={e => setProfile(p => ({ ...p, address: e.target.value }))}
                      className="w-full pl-10 pr-4 py-2.5 bg-gray-50 border border-gray-200 rounded-xl text-sm text-gray-800 placeholder-gray-400 focus:outline-none focus:ring-2 focus:ring-blue-500/20 focus:border-blue-400 transition-all" />
                  </div>
                </div>

                <div className="pt-2 flex items-center gap-3">
                  <button onClick={handleSave}
                    className={`flex items-center gap-2 px-5 py-2.5 rounded-xl text-sm text-white transition-all shadow-md
                      ${saved ? "bg-teal-500 shadow-teal-200" : "bg-blue-600 hover:bg-blue-700 shadow-blue-200"}`}>
                    {saved ? <><Check className="size-4" />Р—Р°РїР°Р·РµРЅРѕ!</> : "Р—Р°РїР°Р·Рё РїСЂРѕРјРµРЅРёС‚Рµ"}
                  </button>
                </div>
              </div>

              {/* Danger zone */}
              <div className="px-6 py-4 border-t border-gray-100 bg-red-50/50">
                <p className="text-sm text-red-700 mb-1">РР·С‚СЂРёРІР°РЅРµ РЅР° Р°РєР°СѓРЅС‚</p>
                <p className="text-xs text-gray-500 mb-3">Р’СЃРёС‡РєРё РґР°РЅРЅРё С‰Рµ Р±СЉРґР°С‚ РёР·С‚СЂРёС‚Рё Р±РµР·РІСЉР·РІСЂР°С‚РЅРѕ</p>
                <button className="flex items-center gap-2 px-4 py-2 rounded-xl bg-white border border-red-200 text-red-600 text-xs hover:bg-red-50 transition-colors">
                  <Trash2 className="size-3.5" />РР·С‚СЂРёР№ Р°РєР°СѓРЅС‚Р°
                </button>
              </div>
            </div>
          )}

          {/* в”Ђв”Ђ Notifications в”Ђв”Ђ */}
          {section === "notif" && (
            <div className="bg-white rounded-2xl border border-gray-100 shadow-sm overflow-hidden">
              <div className="px-6 py-4 border-b border-gray-50">
                <h2 className="text-gray-800">РР·РІРµСЃС‚РёСЏ</h2>
                <p className="text-xs text-gray-400">РР·Р±РµСЂРµС‚Рµ РєРѕРіР° Рё РєР°Рє РґР° РїРѕР»СѓС‡Р°РІР°С‚Рµ РёР·РІРµСЃС‚РёСЏ</p>
              </div>
              <div className="p-6 space-y-1">
                {[
                  { key: "email",    label: "РРјРµР№Р» РёР·РІРµСЃС‚РёСЏ",       desc: "Р’СЃСЏРєРѕ РІР°Р¶РЅРѕ СЃСЉР±РёС‚РёРµ РїРѕ РёРјРµР№Р»" },
                  { key: "sms",      label: "SMS РёР·РІРµСЃС‚РёСЏ",          desc: "РЎСЉРѕР±С‰РµРЅРёСЏ РЅР° С‚РµР»РµС„РѕРЅР°" },
                  { key: "push",     label: "Push РёР·РІРµСЃС‚РёСЏ",         desc: "РР·РІРµСЃС‚РёСЏ РІ Р±СЂР°СѓР·СЉСЂР°" },
                  { key: "messages", label: "РќРѕРІРё С‡Р°С‚ СЃСЉРѕР±С‰РµРЅРёСЏ",    desc: "РљРѕРіР°С‚Рѕ РёР·РїСЉР»РЅРёС‚РµР» РІРё РїРёС€Рµ" },
                  { key: "offers",   label: "РќРѕРІРё РѕС„РµСЂС‚Рё",           desc: "РљРѕРіР°С‚Рѕ РїРѕР»СѓС‡РёС‚Рµ РѕС„РµСЂС‚Р° Р·Р° РїСЂРѕРµРєС‚" },
                  { key: "weekly",   label: "РЎРµРґРјРёС‡РµРЅ РѕС‚С‡РµС‚",        desc: "Р РµР·СЋРјРµ РЅР° РїСЂРѕРµРєС‚РёС‚Рµ РІ РїРµС‚СЉРє" },
                  { key: "updates",  label: "РќРѕРІРёРЅРё Р·Р° РїР»Р°С‚С„РѕСЂРјР°С‚Р°", desc: "РќРѕРІРё С„СѓРЅРєС†РёРё Рё РѕР±РЅРѕРІР»РµРЅРёСЏ" },
                ].map(n => (
                  <div key={n.key} className="flex items-center justify-between py-3.5 border-b border-gray-50 last:border-0">
                    <div>
                      <p className="text-sm text-gray-800">{n.label}</p>
                      <p className="text-xs text-gray-400">{n.desc}</p>
                    </div>
                    <Toggle checked={notifs[n.key as keyof typeof notifs]}
                      onChange={() => setNotifs(ns => ({ ...ns, [n.key]: !ns[n.key as keyof typeof notifs] }))} />
                  </div>
                ))}
              </div>
            </div>
          )}

          {/* в”Ђв”Ђ Security в”Ђв”Ђ */}
          {section === "security" && (
            <div className="space-y-4">
              <div className="bg-white rounded-2xl border border-gray-100 shadow-sm overflow-hidden">
                <div className="px-6 py-4 border-b border-gray-50">
                  <h2 className="text-gray-800">РџСЂРѕРјСЏРЅР° РЅР° РїР°СЂРѕР»Р°</h2>
                </div>
                <div className="p-6 space-y-4">
                  {[
                    { label: "РўРµРєСѓС‰Р° РїР°СЂРѕР»Р°",   ph: "вЂўвЂўвЂўвЂўвЂўвЂўвЂўвЂў" },
                    { label: "РќРѕРІР° РїР°СЂРѕР»Р°",      ph: "РњРёРЅРёРјСѓРј 8 Р·РЅР°РєР°" },
                    { label: "РџРѕС‚РІСЉСЂРґРё РїР°СЂРѕР»Р°С‚Р°", ph: "РџРѕРІС‚РѕСЂРё РЅРѕРІР°С‚Р° РїР°СЂРѕР»Р°" },
                  ].map((f, i) => (
                    <div key={i}>
                      <label className="block text-sm text-gray-700 mb-1.5">{f.label}</label>
                      <div className="relative">
                        <input type={showPass ? "text" : "password"} placeholder={f.ph}
                          className="w-full pr-10 px-4 py-2.5 bg-gray-50 border border-gray-200 rounded-xl text-sm text-gray-800 placeholder-gray-400 focus:outline-none focus:ring-2 focus:ring-blue-500/20 focus:border-blue-400 transition-all" />
                        <button onClick={() => setShowPass(!showPass)}
                          className="absolute right-3 top-1/2 -translate-y-1/2 text-gray-400 hover:text-gray-600 transition-colors">
                          {showPass ? <EyeOff className="size-4" /> : <Eye className="size-4" />}
                        </button>
                      </div>
                    </div>
                  ))}
                  <button className="flex items-center gap-2 px-5 py-2.5 rounded-xl bg-blue-600 text-white text-sm hover:bg-blue-700 transition-colors shadow-md shadow-blue-200">
                    РџСЂРѕРјРµРЅРё РїР°СЂРѕР»Р°С‚Р°
                  </button>
                </div>
              </div>

              <div className="bg-white rounded-2xl border border-gray-100 shadow-sm overflow-hidden">
                <div className="px-6 py-4 border-b border-gray-50">
                  <h2 className="text-gray-800">Р”РІСѓС„Р°РєС‚РѕСЂРЅР° Р°РІС‚РµРЅС‚РёРєР°С†РёСЏ</h2>
                </div>
                <div className="p-6">
                  <div className="flex items-center justify-between mb-4">
                    <div>
                      <p className="text-sm text-gray-800">2FA Р·Р°С‰РёС‚Р°</p>
                      <p className="text-xs text-gray-400">Р”РѕРїСЉР»РЅРёС‚РµР»РЅР° СЃРёРіСѓСЂРЅРѕСЃС‚ РїСЂРё РІР»РёР·Р°РЅРµ</p>
                    </div>
                    <Toggle checked={false} onChange={() => {}} />
                  </div>
                  <div className="flex items-center gap-2 px-3 py-2.5 bg-amber-50 border border-amber-100 rounded-xl">
                    <Shield className="size-4 text-amber-500 flex-shrink-0" />
                    <p className="text-xs text-amber-700">РџСЂРµРїРѕСЂСЉС‡РІР°РјРµ 2FA Р·Р° РїРѕ-РІРёСЃРѕРєР° СЃРёРіСѓСЂРЅРѕСЃС‚ РЅР° Р°РєР°СѓРЅС‚Р°</p>
                  </div>
                </div>
              </div>
            </div>
          )}

          {/* в”Ђв”Ђ App settings в”Ђв”Ђ */}
          {section === "app" && (
            <div className="bg-white rounded-2xl border border-gray-100 shadow-sm overflow-hidden">
              <div className="px-6 py-4 border-b border-gray-50">
                <h2 className="text-gray-800">РќР°СЃС‚СЂРѕР№РєРё РЅР° РїСЂРёР»РѕР¶РµРЅРёРµС‚Рѕ</h2>
              </div>
              <div className="p-6 space-y-1">
                {[
                  { label: "РўСЉРјРµРЅ СЂРµР¶РёРј",        desc: "РџСЂРµРІРєР»СЋС‡Рё РјРµР¶РґСѓ СЃРІРµС‚СЉР» Рё С‚СЉРјРµРЅ РёР·РіР»РµРґ", disabled: true, hint: "РЎР°РјРѕ СЃРІРµС‚СЉР» СЂРµР¶РёРј" },
                  { label: "РљРѕРјРїР°РєС‚РµРЅ РёР·РіР»РµРґ",   desc: "РџРѕ-РјР°Р»РєРё РєР°СЂС‚Рё Рё РїРѕ-РїР»СЉС‚РЅР° РёРЅС„РѕСЂРјР°С†РёСЏ", disabled: false },
                  { label: "РђРЅРёРјР°С†РёРё",           desc: "РџР»Р°РІРЅРё РїСЂРµС…РѕРґРё Рё РµС„РµРєС‚Рё", disabled: false },
                ].map((s, i) => (
                  <div key={i} className="flex items-center justify-between py-3.5 border-b border-gray-50 last:border-0">
                    <div>
                      <div className="flex items-center gap-2">
                        <p className="text-sm text-gray-800">{s.label}</p>
                        {s.hint && <span className="px-2 py-0.5 rounded-md bg-gray-100 text-gray-500 text-xs">{s.hint}</span>}
                      </div>
                      <p className="text-xs text-gray-400">{s.desc}</p>
                    </div>
                    <Toggle checked={!s.disabled} onChange={() => {}} />
                  </div>
                ))}
                <div className="py-3.5 flex items-center justify-between border-b border-gray-50">
                  <div>
                    <p className="text-sm text-gray-800">Р•Р·РёРє</p>
                    <p className="text-xs text-gray-400">Р•Р·РёРєСЉС‚ РЅР° РёРЅС‚РµСЂС„РµР№СЃР°</p>
                  </div>
                  <div className="flex items-center gap-2">
                    <Globe className="size-4 text-gray-400" />
                    <span className="text-sm text-gray-700">Р‘СЉР»РіР°СЂСЃРєРё</span>
                  </div>
                </div>
              </div>
              <div className="px-6 py-4 border-t border-gray-50 bg-gray-50/50">
                <p className="text-xs text-gray-400">TemaDom v1.0.0 В· <a href="#" className="text-blue-600 hover:underline">РЈСЃР»РѕРІРёСЏ</a> В· <a href="#" className="text-blue-600 hover:underline">РџРѕРІРµСЂРёС‚РµР»РЅРѕСЃС‚</a></p>
              </div>
            </div>
          )}

        </div>
      </div>
    </div>
  );
}
